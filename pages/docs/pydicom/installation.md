---
title: Pydicom Installation
sidebar: pydicom
permalink: pydicom-install
folder: docs
---

{% include toc.html %}


As a pure python package, pydicom is easy to install and has no
requirements other than python itself (the NumPy library is recommended,
but is only required if manipulating pixel data). In addition to the instructions below, pydicom can also be installed through the  <a href="http://www.pythonxy.com/" target="_blank">Python(x,y)</a> 
distribution, which can install python and a number of packages [^1]  (including pydicom) at once.


### Prerequisites

 * python 2.6, 2.7, 3.3 or later
 * <a href="http://numpy.scipy.org" target="_blank">NumPy</a> -- optional, only needed if manipulating pixel data 

To run unit tests when using python 2.6, <a href="https://pypi.python.org/pypi/" target="_blank"> unittest2">Unittest2</a> is required. Python installers can be found at the <a href="http://python.org/download/" target="_blank"> python web site</a>. On Windows, the <a href="http://activestate.com/activepython">Activepython</a> distributions are also quite good.


### All Platforms 

#### Installing using pip
The easiest way to install pydicom is using <a href="https://pypi.python.org/pypi/pip" target="_blank">
pip</a>

```bash
pip install pydicom
```

Depending on your python version, there may be some warning messages,
but the install should still be ok. Note that Pip comes pre-installed with Python 3.x.


#### Installing from source

Download <a href="https://github.com/pydicom/pydicom/archive/master.zip">the source code directly</a> or, or clone as follows:

```bash
git clone https://www.github.com/pydicom/pydicom.git
cd pydicom
python setup.py install
```

If you are installing to a system python, then you will need to use sudo:

```bash
sudo python setup.py install
```

It is recommended that you use a virtual environment, such as <a href="https://www.continuum.io/downloads" target="_blank">Anaconda</a>.


### Installing on Mac

Using pip as described above is recommended.  However, there was previously a
<a href="https://www.macports.org/ports.php?by=library&substr=py27-pydicom" target="_blank">MacPorts portfile</a> This is maintained by other users and may not immediately be up to
the latest release.


## Next Steps
To start learning how to use pydicom, see the <a href="/pydicom-getting-started">pydicom getting started</a> page.

[^1]: If using python(x,y), other packages you might be interested in include <a href="https://ipython.org/install.html" target="_blank">IPython</ah> (an indispensable interactive shell with auto-completion, history etc), <a href="http://www.numpy.org/" target="_blank">Numpy</a> (optionally used by pydicom for pixel data), and <a href="https://itk.org/" target="_blank">ITK/VTK</a> or <a href="https://github.com/python-pillow/Pillow" target="_blank">PIL</a> (image processing and visualization).
