# Access to Software

## Accessing Scientific Software (quarantine aka modules)

All computer systems have installed a standard suite of desktop productivity software
(office, image manipulation, web browser, etc.). If a readily available productivity
software package is not installed and you wish to use it,
[open a support ticket](https://discourse.douglasneuroinformatics.ca/) to request
installation.

Scientific software is deployed across all computers in the platform via shared network
drive, ensuring the same version of software is run on all machines during any kind of
cluster processing. To make multiple versions of software available, software is isolated
in separate installation directories and access is managed via the
[`module`](https://modules.readthedocs.io/en/latest/) system.
The `module` system allows for multiple versions to live side-by-side, for dependencies
between software to be specified, and for conflicting versions to be specified.

```{admonition} On which machines is the quarantine available?
The software quarantine (aka modules) is available on workstation systems (`cicwsNN`) and the compute nodes (`ciccsNN`).

It is not available on the login or storage servers as scientific processing should not take place there.
```



The obtain a list of available software, run `module avail`, below is an example generated
on 2022-11-01, the format of the naming below is `<modulename>/<moduleversion>`:

```{code-block}

-------------------------------------------------------------------------------------------- /opt/quarantine/modules ---------------------------------------------------------------------------------------------
AFNI/20220609                      R/4.1.3                       itksnap/4.0.0-20220623-nightly
ANTs/2.4.0                  (D)    RMINC/v1.5.3.0                julia/1.8.2
ANTs/20220513                      SDM/6.22                      mango/4.1
CAT12/r2043                        SPM12/r7771                   minc-stuffs/v0.1.25
CIVET/2.1.1                        anaconda/2022.05              minc-toolkit-extras/1.0
FID-A/1.2                          bart/0.7.00                   minc-toolkit-v2/1.9.18.2
FSL/6.0.5.1                        bpipe/0.9.11                  mrtrix3/3.0.3
GlobusConnectPersonal/3.1.6        brkraw/0.3.5           (D)    mrtrix3tissue/5.2.9
INSPECTOR/20201115                 brkraw/20220210               plink/1.07
MATLAB/R2021a                      dcm2niix/v1.0.20211006        pydpiper/v2.0.16
MATLAB/R2022a               (D)    fiji/20220414-1745            pyminc/v0.56
MRIcroGL/v1.2.20211007             fmriprep/20.2.7               qbatch/2.3
MRIcron/v1.2.20211006              fmriprep/22.0.0        (D)    remotemesa/1.0
MVGC/1.3                           freesurfer/7.2.0              rstudio/2022.02.3+492
PLS/6.15.1                         gift/4.0.3.0                  tapas/6.0.1
PyQC/3.0                           imagej/20220414-1745
```

To load a module, use the load command, `module load <modulename>` which will load the default version `(D)` if it is specified in the module
system, otherwise it will load the latest version. To load a specific version of a module, specify the version during loading,
`module load <modulename>/<moduleversion>`.

```{admonition} Module Dependencies
If you try to load a module which has dependencies you have not yet satisfied, you will receive an error that will specify the dependencies and
modules available that would satisfy it, each missing dependency stops the module loading so this may occur several times as you load all dependencies:

```{code-block} bash

$ module load pyminc
pyminc/0.51(7):ERROR:151: Module 'pyminc/0.51' depends on one of the module(s) 'anaconda/miniconda3 anaconda/5.1.0-python3 anaconda/5.0.1-python3 anaconda/4.3.0-python2.7 anaconda/4.2.0-python3 anaconda/4.1.1 anaconda/2019.03-python3 anaconda/2.5 anaconda/2.3 anaconda/2.1.0 anaconda/2.0.1'
pyminc/0.51(7):ERROR:102: Tcl command execution failed: prereq anaconda

```
