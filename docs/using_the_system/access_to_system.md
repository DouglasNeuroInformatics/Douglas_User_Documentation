# Accessing the System

The platform can be accessed in a number of ways:

1. Physical access
2. Remote access within the Douglas

## Physical Access

Physical access to a suite of workstations is available inside the Douglas CIC,
contact the CIC Administrative Assistant (Louis Théroux) <louis.theroux.comtl@ssss.gouv.qc.ca> for keycard access.

## Remote Access within the Douglas

All platform hardware is accessible within the Douglas Research Centre network
via `ssh`. The main user server is available at `cicus03`, the storage server
at `cicss05` and workstations are available in the range `cicws[01..48]` and
`dnpws[01..12]`.

```{admonition} Playing nice
Neuroinformatics workstations all allow for multiple simultaneous users, please
make a best effort to choose a workstation not already being used by others.

The command [`who`](https://linuxize.com/post/who-command-in-linux/) can list
currently logged-in users, while [`htop`](https://htop.dev/) will show
a graphical display of the current state of CPU and Memory utilization.

In general, fewer users is better, as well as low CPU and
memory utilization (represented by the length of the horizontal coloured bars
in `htop`)

```

### Graphical Access

In addition to shell access on workstations via SSH, access to a full graphical
desktop is available via [X2GO](https://wiki.x2go.org/doku.php) which rides on SSH.
Install the local client, create a connection to a workstation and specify
the LXDE desktop type for a minimal-graphical-features remote desktop
with features equivalent to sitting at a workstation.
