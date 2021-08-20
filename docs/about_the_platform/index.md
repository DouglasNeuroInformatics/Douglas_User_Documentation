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
and a large suite of scientific software. Servers run Ubuntu Linux server, as well as
compute nodes. Limited Windows workstations are available to provide access to proprietary
software such as E-Prime. Scientific software is available in the
{ref}`software quarantine<using_the_system/access_to_software:accessing scientific software (quarantine aka modules)>`.
