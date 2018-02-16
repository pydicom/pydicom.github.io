# Pydicom

![images/logo/logo.png](images/logo/logo.png)

This is the home of the [Pydicom documentation](https://pydicom.github.io). If you are a Python developer looking to get started with Dicom and Python, this will be the place to learn and contribute! For now, here are some helpful links, and general plan for some of the code bases in the organization.

## Software

 - [pydicom](https://github.com/pydicom/pydicom): The best software in python I've found to work with dicom (datasets) is pydicom. There is substantial [documentation](https://pydicom.github.io/pydicom) if you want to get started.
 - [pynetdicom3](https://github.com/scaramallion/pynetdicom3): is where you want to start if you want to create Service Class Providers (SCPs) or Service Class Users (SCUs). These are the little servers/processes that echo/store/move/find dicom datasets around. This is the bread and butter of the protocol, and is based on the original [pynetdicom](https://github.com/patmun/pynetdicom). We will hopefully consolidate these two so that it is less confusing.


## Containers
We will be developing different dicom applications that are container-based. This means using [Docker](https://docs.docker.com/get-started/) and [Singularity](https://singularityware.github.io) to easily deploy servers (more suited for Docker), and general tools and applications (Singularity is more suited for tools on shared resources).

### Singularity Dicom
[Singularity Dicom](https://github.com/pydicom/singularity-dicom) This will be a "quick start" image that you can build to easily start using some basic tools for working with dicom files. Currently, the image just installs the [Dicom ToolKit](http://support.dcmtk.org/docs/).

## APIs

### Dicom Cookies
As a new person to Dicom, I found it hard to find and programatically download a quick (and maybe fun?) Dicom dataset. Toward this goal, I created a statically served [Dicom Cookies](https://github.com/pydicom/dicom-cookies) dataset. The human readable entrypoint is [here](https://pydicom.github.io/dicom-cookies/), and you can see it being used programatically [here](https://asciinema.org/a/122503?speed=3).

## Coming Soon
I (@vsoch) will be creating a set of web application (Dockerized) to be deployed in different cloudy places to work with Dicom. I'm new to most of this, so will take some time to learn of course. You can expect this README to be replaced with a more suitable site soon!


## Please Contribute and Join!
If you are interested in medical imaging, python, or dicom, please join the organization! 
