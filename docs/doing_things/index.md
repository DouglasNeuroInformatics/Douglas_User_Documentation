# Doing Things

## <a name="systemAccess"></a>Accessing the System

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

## <a name="dataTransfer"></a>Transferring Data

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
days from the date of the acquisition in `/opt/<PV version>/data/<username>`, 
with `<PV version>` the ParaVision software version (PV5.1 or PV6.0.1) and `<username>` 
the login of the user performing the scans. Users are expected to access their data 
during that time and copy it to appropriate long term storage. Recovery is available 
with delayed access and a recovery fee associated with staff time. You can access 
the data by 1) accessing the [Neuroinformatics Platform](#systemAccess) and then 2) 
accessing the bruker7t computer. The [tools for data transfer](#dataTransfer) will 
work.

Conversion to other formats (dicom and nifti) is availaible upon request.
  
  




## Accessing Scientific Software (quarantine aka modules)

All computer systems have installed a standard suite of desktop productivity software
(office, image maniupuation, web browser, etc.). If a readily available productivity
software package is not installed and you wish to use it, please contact us to request
installation.

Scientific sofware is deployed across all computers in the platform via shared network
drive, ensuring the same version of software is run on all machines during any kind of
cluster processing. To make multiple versions of software available, software is isolated
in seperate installation directories and access is managed via the `module` system.
The `module` system allows for multiple versions to live side-by-side, for dependencies
between software to be specified, and for conflicting versions to be specified.

The obtain a list of available software, run `module avail`, below is an example generated
on 2021-06-09, the format of the naming below is `<modulename>/<moduleversion>`:

```{code-block}

-------------------------------------------------------------------------------------------- /opt/quarantine/modules ---------------------------------------------------------------------------------------------
ACVD/20161025                                        jmrui/6.0beta                                        pyminc/0.41
AFNI/2014.09.08.21.47EDT                             mango/3.8                                            pyminc/0.42b
AFNI/2017.03.30.07.57EDT                             mango/4.0.1                                          pyminc/0.46
AllenGeneMNI/dev                                     matlab/R2012a                                        pyminc/0.47
anaconda/2.0.1                                       matlab/R2014a                                        pyminc/0.48
anaconda/2019.03-python3                             matlab/R2015aSP1                                     pyminc/0.49
anaconda/2.1.0                                       matlab/R2016a                                        pyminc/0.51
anaconda/2.3                                         matlab/R2018b                                        PyQC/1.0
anaconda/2.5                                         mi-brain/2020.04.09                                  qbatch/2.1.3
anaconda/4.1.1                                       MIDER/v2                                             qbatch/2.1.5
anaconda/4.2.0-python3                               minclaplace/a280379ff13d8265a9ca342cfa6f4510c24d26b8 qbatch/2.2
anaconda/4.3.0-python2.7(default)                    minc-stuffs/0.1.12^minc-toolkit-1.9.10               quarantine
anaconda/5.0.1-python3                               minc-stuffs/0.1.12^minc-toolkit-1.9.11               R/3.1.1
anaconda/5.1.0-python3                               minc-stuffs/0.1.15a^minc-toolkit-1.9.11              R/3.2.1
anaconda/miniconda3                                  minc-stuffs/0.1.16^minc-toolkit-1.9.11               R/3.2.4
ANTs/20190211                                        minc-stuffs/0.1.20^minc-toolkit-1.9.11               R/3.3.3
ANTs/20191007                                        minc-stuffs/0.1.20^minc-toolkit-1.9.15               R/3.4.0
ANTs/20191119                                        minc-stuffs/0.1.21^minc-toolkit-1.9.15               R/3.5.0
ANTs/20200104                                        minc-stuffs/0.1.22^minc-toolkit-1.9.16               R/3.5.1
ANTs/20200227                                        minc-stuffs/0.1.24^minc-toolkit-1.9.16               remotemesa/1.0
ANTs/20200410                                        minc-stuffs/0.1.24^minc-toolkit-1.9.17               R-extras/3.1.1
ANTs/2.1.0                                           minc-stuffs/0.1.4^minc-toolkit-1.0.01                R-extras/3.2.1
ANTs/2.1.0rc3                                        minc-stuffs/0.1.7^minc-toolkit-1.0.01                R-extras/3.2.3
ANTs/2.2                                             minc-stuffs/0.1.9^minc-toolkit-1.9.10                R-extras/3.2.4
ANTs/2.3.1                                           minc-toolkit/1.0.01                                  R-extras/3.3.3
bpipe/0.9.8.6                                        minc-toolkit/1.0.04                                  R-extras/3.4.0
bpipe/0.9.8.7                                        minc-toolkit/1.0.07                                  RMINC/1.2.4.5^minc-toolkit-1.0.01^R-3.1.1
bpipe/0.9.9                                          minc-toolkit/1.9.10                                  RMINC/1.2.4.7^minc-toolkit-1.0.01^R-3.1.1
bpipe/0.9.9.2                                        minc-toolkit/1.9.10.1                                RMINC/1.2.4.9^minc-toolkit-1.9.10^R-3.2.1
bpipe/0.9.9.3                                        minc-toolkit/1.9.11                                  RMINC/1.3.0.0^minc-toolkit-1.9.10^R-3.2.1
bpipe/0.9.9.4                                        minc-toolkit/1.9.15                                  RMINC/1.3.0.0^minc-toolkit-1.9.11^R-3.2.4
bpipe/0.9.9.5                                        minc-toolkit/1.9.16                                  RMINC/1.4.0.0^minc-toolkit-1.9.11^R-3.2.4
bpipe/0.9.9.6                                        minc-toolkit/1.9.17                                  RMINC/1.4.0.3^minc-toolkit-1.9.11^R-3.2.4
BrainExplorer/2                                      minc-toolkit-extras/1.0                              RMINC/1.4.1.1^minc-toolkit-1.9.11^R-3.2.4
braingl/0.0-1                                        miniconda/2020-03                                    RMINC/1.4.2.0^minc-toolkit-1.9.11^R-3.2.4
braingl/dev                                          MIPAV/6.0.1                                          RMINC/1.4.3.0^minc-toolkit-1.9.11^R-3.2.4
brain-view2/1.0^minc-toolkit-1.0.01                  MIPAV/7.1.1                                          RMINC/1.4.3.1^minc-toolkit-1.9.11^R-3.2.4
brain-view2/1.0^minc-toolkit-1.9.10                  MIPAV/7.2.0                                          RMINC/1.4.3.2^minc-toolkit-1.9.11^R-3.2.4
Bru2Nii/1.0.20170707                                 mni.cortical.statistics/0.9.4                        RMINC/1.4.3.3^minc-toolkit-1.9.11^R-3.2.4
c3d/2015.06.22                                       mountainlab/20171005                                 RMINC/1.4.3.4^minc-toolkit-1.9.11^R-3.2.4
CIVET/1.1.10                                         mricrogl/12-February-2016                            RMINC/1.4.4.0^minc-toolkit-1.9.15^R-3.3.3
CIVET/1.1.12                                         mricrogl/12-June-2015                                RMINC/1.5.0.0^minc-toolkit-1.9.15^R-3.4.0
CIVET/2.1.0                                          mricron/1JUNE2015                                    RMINC/1.5.1.0^minc-toolkit-1.9.16^R-3.4.0
CIVET-extras/1.0                                     mricron/22DEC2015                                    RMINC/1.5.2.0^minc-toolkit-1.9.16^R-3.5.0
cmake/3.10.2                                         MRO/3.2.3                                            RMINC/1.5.2.1^minc-toolkit-1.9.16^R-3.5.0
cmake/3.13.1                                         mrtrix3/3.0_rc3_30c24e3                              RMINC/1.5.2.1^minc-toolkit-1.9.16^R-3.5.1
dcm2niix/1.0.20171215                                mrtrix3/d861bbe6                                     RMINC/1.5.2.2^minc-toolkit-1.9.17^R-3.5.1
dcm2niix/1.0.20181125                                MVGC/1.0                                             RMINC/1.5.2.3^minc-toolkit-1.9.17^R-3.5.1
dcm2niix/1.0.20190902                                niak/v0.13.5                                         rstudio/0.98.1103
dcm2niix/1.0.20200331                                niftimatlib/1.2                                      rstudio/0.99.491
DKE/2015.10.28                                       NODDI_toolbox/0.9                                    rstudio/0.99.896
DKE-ft/2015.10.26                                    octave/4.0.2                                         rstudio/0.99.903
fmristat/2006.06.06                                  paraview/5.0.0                                       rstudio/1.0.136
freesurfer/5.3.0                                     PLINK/1.0.7                                          rstudio/1.0.143
freesurfer/6.0                                       PLINK/201502                                         rstudio/1.1.383
FSL/5.0.6                                            PLS/6.1311050                                        rstudio/1.1.453
FSL/5.0.7                                            PLS/6.15                                             rstudio/1.1.463
FSL/5.0.8                                            pvconv/0.57                                          SGE-extras/1.0
FSL/5.0.9                                            pycharm/2017.2.1                                     shapeit/2r790
FSL/6.0.2                                            pydpiper/1.10                                        singularity/2.6.1
gcc/4.1.2                                            pydpiper/1.11                                        snptest/2.5
gift/4.0a                                            pydpiper/1.13.1                                      SPAMS/2.5
git/2.1.0                                            pydpiper/1.14-beta1                                  SPM/12b_r6080
git/2.3.0                                            pydpiper/1.14-beta2                                  SPM/12b_r6225
gradunwarp/1.0.2                                     pydpiper/1.15                                        SPM/8_r5236
GreatApes/dev                                        pydpiper/1.18                                        SPM12/r6080
GTOOL/0.7.5                                          pydpiper/2.0.1                                       SPM12/r6225
HCP_ConnectomeWorkbench/1.3.2                        pydpiper/2.0.10                                      SPM12/r6685
ilastik/1.3.3post3                                   pydpiper/2.0.12                                      SPM12/r7219
ILT/4bc2d846                                         pydpiper/2.0.13                                      SPM8/r5236
impute/2.3.2                                         pydpiper/2.0.3                                       SPM8/r6313
itksnap/3.2.0                                        pydpiper/2.0.5                                       torch/d3b017d2aba6a865f44caf1b8e5f07996c26d4c0
itksnap/3.4.0-minc                                   pydpiper/2.0.6                                       webp/1.1.0
itksnap/3.6.0                                        pydpiper/2.0.8
java/8u171-32bit                                     pyminc/0.4
```

To load a module, use the load command, `module load <modulename>` which will load the deafault version `(D)` if it is specified in the module
system, otherwise it will load the latest version. To load a specific version of a module, specify the version during loading,
`module load <modulename>/<moduleversion>`.

```{admonition} Module Dependencies
If you try to load a module which has dependencies you have not yet satisfied, you will receive an error that will specify the dependencie and
modules available that would satisfy it, each missing depndency stops the module loading so this may occur several times as you load all dependencies:

```{code-block} bash

$ module load pyminc
pyminc/0.51(7):ERROR:151: Module 'pyminc/0.51' depends on one of the module(s) 'anaconda/miniconda3 anaconda/5.1.0-python3 anaconda/5.0.1-python3 anaconda/4.3.0-python2.7 anaconda/4.2.0-python3 anaconda/4.1.1 anaconda/2019.03-python3 anaconda/2.5 anaconda/2.3 anaconda/2.1.0 anaconda/2.0.1'
pyminc/0.51(7):ERROR:102: Tcl command execution failed: prereq anaconda

```

```
