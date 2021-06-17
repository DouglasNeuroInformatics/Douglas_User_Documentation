# About the platform

The Douglas Neuroinformatics Platform is a single-sign-on Ubuntu Linux based
computer system. Originally the computing platform of the Douglas Cerebral
Imaging Center (CIC), it has grown and generalized to meet the informatics
needs of the Douglas Research Center as a whole.

## Hardware

The system itself consists (as of mid-2021) of Linux-based single-sign-on
user management system, along with a 1 PB storage system, ~40 8-12 core
workstations with 16-32 GB of RAM, and a 10-node compute cluster of
12-core 48 GB RAM compute nodes. Primary servers are replicated across
two sites for disaster recovery. Unified storage across systems is
provided via NFS from the primary storage server to all systems.
A heterogenous cluster compute environment is provided via a SLURM
batch system providing access to the compute cluster as well as opportunistic
scheduling on workstations.

Entry-level GPU computation is available on workstations to provide CUDA
and OpenCL acceleration suitable applications.

## Software

The platform workstations run Ubuntu Linux variants, with full productivity
software (LibreOffice, GIMP, Inkscape, etc), modern web browsers (Chrome, Firefox),
and a large suite of scientific software. Scientific software is avaialble in the
{ref}`software quarantine<doing_things/index:accessing scientific software (quarantine aka modules)>`.

## Filesystem layout

Each computer in the system has access to two system-wide network filesystems.
User home directories `$HOME` are mounted from the user server (currently `cicus03`).
Home directories are suitable for storing the regular confiugration files, as well
as papers and similar files, it should not be used to store data. The high performace
filesystem (currently hosted on `cicss03`) is available under the `/data` path.
All users have access to scratch storage at `/data/scratch`, which is suitable
for storing data during processing. Scratch does not keep any historical versions
and is not backed up, so it should not be relied upon for long-term storage. In
the future it is expected a date-based deletion policy will be implemented.
