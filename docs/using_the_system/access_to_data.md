# Access to Data

## Filesystem Layout

Each computer in the system has access to two system-wide network filesystems.
User home directories `$HOME` are mounted from the user server (currently `cicus03`)
on `/home/cic/<username>`. Home directories are suitable for storing the regular configuration files, as well
as papers and similar files, it should not be used to store data.

The high performance filesystem (currently hosted on `cicss05`) is available under the `/data` path.
All users have access to scratch storage at `/data/scratch2`, which is suitable
for storing data during processing. Scratch does not keep any historical versions
and is not backed up, so it should not be relied upon for long-term storage. In
the future it is expected a age-based deletion policy will be implemented to
maintain sufficient free space and encourage users to use storage properly.

Paid storage for individual lab groups is also available under the `/data/` path,
the exact name depends upon what the group decided during creation.

```{admonition} Mounting on demand
Network filesystems are not automatically mounted on boot-up on machines, but
rather mounted lazily on-demand. As such, `/data` will appear empty before
attempts are made to access a specific filesystem. GUI file managers do
not work particularly well in this scenario, as there will be no folders
to interact with. It is recommended to perform file management using the
command line tools.
```

## Transferring Data

Access to filesystems is enabled via the `scp/sftp` functionality of `ssh`, as
well as the `rsync` program over `ssh`. Linux and OSX users can find the `sftp`
`scp` and `rsync` commands in their terminal. Windows users can use
[WinSCP](https://winscp.net/) or [FileZilla](https://filezilla-project.org/)
for a graphical tool to access data or [MobaXterm](https://mobaxterm.mobatek.net/)
for a proper Linux-like terminal.

Here are few example commands for data transfer, note that these commands assume that
you are within the Douglas:

```bash
# Copying a directory of files to cicss05 in /data/scratch/<username>
$ rsync -avz directory <username>@cicss05:/data/scratch/<username>
# Copying another directory from cicss05 to your local system
$ rsync -avz <username>@cicss05:/data/scratch/<username>/another_dir .
```

```{admonition} Resumable file transfers
`rsync` is strongly recommended for all data transfers, as it supports resuming interrupted transfers
```

```{admonition} Bulk data transfer
For bulk data transfers, please connect directly to `cicss05` to bypass any round-trip data would need to travel if
performing transfers to workstations.
```

```{admonition} Real time data access
The [sshfs](https://github.com/libfuse/sshfs) project allows for filesystems to be mounted remotely via ssh.
This allows you to access files without having to explicitly transfer them back-and-forth.
See the site for details and for windows see [here](https://github.com/billziss-gh/sshfs-win).

```

## Accessing Human MRI Scanner DICOMS

The Siemens MAGNETOM Prisma Human MRI scanner sends collected data to `cicus03`
which acts a pseudo-PACS system, collecting the files and storing them at
`/home/cic/dicom/transfers` accessible for 14 calendar days before being moved
to long-term cold storage. Users are expected to access their data during that
time and copy it to appropriate long term storage. Recovery from cold storage
is available with delayed access and a recovery fee associated with staff time.


## Accessing Animal MRI Scanner Raw Data

The Bruker BioSpec 70/30 scanner produces data in the raw Bruker data format. 
The data sets are accessible on the Bruker controlling computer for 14 calendar
days from the date of the acquisition at `/opt/<PV version>/data/<username>`, 
with `<PV version>` the ParaVision software version (PV5.1 or PV6.0.1) and `<username>` 
the login of the user performing the scans. Users are expected to access their data 
during that time and copy it to appropriate long term storage. Recovery is available 
with delayed access and a recovery fee associated with staff time. Data can be accessed
by 1) accessing the {ref}`Neuroinformatics Platform<using_the_system/access_to_system:accessing the system>` and then 2) 
accessing the bruker7t computer. The {ref}`tools for data transfer<using_the_system/access_to_data:transferring data>` will 
work, provided you take into account you need to connect to an additional computer (the bruker7t). 
The bruker7t ssh version is old (OpenSSH_4.3p2, OpenSSL 0.9.8e-fips-rhel5 01 Jul 2008). 
Depending on your local ssh version, you might need to add these options to ssh calls:
`-oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-dss`.
We suggest that you add these lines to your `~/.ssh/config` file:
```
Host bruker7t
    KexAlgorithms diffie-hellman-group1-sha1
    HostKeyAlgorithms ssh-rsa
```
This way, you can use the host `bruker7t` in your ssh and rsync calls without 
specifying additional options.

Conversion to other formats (DICOM and NIFTI) is available upon request.
