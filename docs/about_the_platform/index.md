# About the platform

The Douglas Neuroinformatics Platform is a single-sign-on Ubuntu Linux based
computer system. Originally the computing platform of the Douglas **Cerebral
Imaging Centre** (CIC), it has grown and generalized to meet the informatics
needs of the **Douglas Research Centre** (DRC) as a whole.

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

## Services

Beyond core computing, the platform hosts a suite of specialized web-based services designed to streamline data collection and management. These include **ChatDNP**, a privacy-focused local AI assistant; the **Open Data Bank (ODB)** for versioning and sharing tabular datasets; and **Open Data Capture (ODC)** for the digital administration of clinical research instruments. 

For more details on these tools and how to access them, please see the {ref}`Available Services <available_services/index:Available Services>` section.
