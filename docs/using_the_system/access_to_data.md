# Access to Data

## Transferring Data

Access to filesystems is enabled via the `scp/sftp` functionality of `ssh`, as
well as the `rsync` program over `ssh`. For data transfers, please connect
directly to `cicss03` to bypass any round-trip data would need to travel if
performing transfers to workstations. Linux and OSX users can find the `sftp`
`scp` and `rsync` commands in their terminal. Windows users can use
[WinSCP](https://winscp.net/) or [FileZilla](https://filezilla-project.org/)
for a graphical tool to access data.

```{admonition} Real time data access
The [sshfs](https://github.com/libfuse/sshfs) project allows for filesystems to be mounted remotely via ssh. See the site for details and for windows see [here](https://github.com/billziss-gh/sshfs-win).

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
by 1) accessing the {ref}`Neuroinformatics Platform<doing_things/index:accessing the system>` and then 2) 
accessing the bruker7t computer. The {ref}`tools for data transfer<doing_things/index:transferring data>` will 
work, provided you take into account you need to connect to an additional computer (the bruker7t).

Conversion to other formats (DICOM and NIFTI) is available upon request.
