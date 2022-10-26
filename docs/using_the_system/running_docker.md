# Running Docker

Docker is installed on the DNP system. However, for security reasons, it must be configured to run in non-root mode.

## Configuration

First, run the install script `dockerd-rootless-setuptool.sh`, located in `/usr/bin`, to set up the daemon: 

```
$ dockerd-rootless-setuptool.sh install
```

Next, it is necessary to specify an alternative path for docker to store data. The default directory for this is `~/.local/share/docker`. However, as user directories are on a Network File System (NFS), this must be changed. 

This is set in the file `.config/docker/daemon.json`, which for a new user should not exist. If it does exist, adjust the following procedure as needed. Otherwise, we can create a new directory in `/scratch` as follows:

```
$ export DOCKER_DATA_ROOT=/scratch/$(whoami)/docker/data
$ mkdir -p $DOCKER_DATA_ROOT
$ printf "{\"data-root\": \"%s\"}\n" $DOCKER_DATA_ROOT > .config/docker/daemon.json
```

Please note, if for any reason, the docker was already running on your user account prior to adjusting the daemon configuration, you must restart the daemon for these changes to take effect.

```
$ systemctl --user stop docker
```

```{admonition} Before Continuing
:class: warning

Be aware that /scratch only exists on the local system you're using and it will therefore not be accessible from other workstations. 

```

## Usage

Docker provides a tutorial image that we can use to test the above configuration. First, start the docker daemon:

```
$ systemctl --user start docker
```

Then, using the following command, you can pull the tutorial image, specifying the flags `-d` to run the container in detached mode (i.e., in the background), and `-p` to map port 80 of the container to the non-privileged port 8080. If everything works correctly, you should see the ID for the container printed to stdout.

```
$ docker run -d -p 8080:80 docker/getting-started
816cf0803527656228a85e0a379a54a0086a4885dd0fa9b2dc42c0b7b6cc1c9b`
```

If you are new to docker, navigate to `localhost:8080` and follow the tutorial in your browser.

## Troubleshooting

If you encounter any errors throughout this process, please refer to the [official documentation](https://docs.docker.com/engine/security/rootless/) for running docker in non-root mode.
