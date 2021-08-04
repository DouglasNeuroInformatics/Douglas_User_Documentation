## Accessing the System

The platform can be accessed in a number of ways:

1. Physical access
2. Remote access within the Douglas.
3. Remote access outside the Douglas.

### Physical Access

Physical access to a suite of workstations is available inside the Douglas CIC,
contact the CIC Administrative Assistant (Louis Théroux) for keycard access.

### Remote Access within the Douglas

All platform hardware is acccessible within the Douglas Research Center network
via `ssh`. The main userserver is available at `cicus03`, the storage server
at `cicss03` and workstations are available in the range `cicws[01..41]`.

```{admonition} Playing nice
Neuroinformatics workstations all allow for multiple simultaneous users, please
make a best effort to choose a workstation not already being used by others.

The command `who` can list currently logged-in users, while `htop` will show
a graphical display of the current state of CPU and Memory utilization.
```

### Remote Access outside the Douglas

Remote access from outside the Douglas is provided by authorization only.
Please contact the platform to request access.