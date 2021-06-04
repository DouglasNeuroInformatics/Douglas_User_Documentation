# About the platform

The Douglas Neuroinformatics Platform is a single-sign-on Ubuntu Linux based
computer system. Originally the computing platform of the Douglas Cerebral
Imaging Center (CIC), it has grown and generalized to meet the informatics
needs of the Douglas Research Center as a whole.

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
