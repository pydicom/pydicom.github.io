---
title: Introduction to Pydicom
sidebar: pydicom
permalink: pydicom-introduction
folder: docs
---

## Introduction

pydicom is a pure python package for working with <a href="http://en.wikipedia.org/wiki/DICOM" target="_blank">DICOM</a> files such as medical images, reports, and radiotherapy objects.

pydicom makes it easy to read these complex files into natural pythonic structures for easy manipulation. Modified datasets can be written again to DICOM format files.


{% include toc.html %}


Here is a simple example of using pydicom in an interactive session, to read
a radiotherapy plan file, change the patient setup from head-first-supine to
head-first-prone, and save to a new file:

```python
>>> from pydicom import dicomio
>>> ds = dicomio.read_file("rtplan.dcm")  # plan dataset
>>> ds.PatientName
'Last^First^mid^pre'

>>> ds.dir("setup")    # get a list of tags with "setup" somewhere in the name
['PatientSetupSequence']

>>> ds.PatientSetupSequence[0]
(0018, 5100) Patient Position                    CS: 'HFS'
(300a, 0182) Patient Setup Number                IS: '1'
(300a, 01b2) Setup Technique Description         ST: ''

>>> ds.PatientSetupSequence[0].PatientPosition = "HFP"
>>> ds.save_as("rtplan2.dcm")
```

pydicom is not a DICOM server [^1], and is not primarily about viewing images. It is designed to let you manipulate data elements in DICOM files with python code.

pydicom is easy to install and use, and because it is a pure
python package, it should run anywhere python runs.

One limitation of pydicom: compressed pixel data (e.g. JPEG)
cannot be altered in an intelligent way as it can be for uncompressed pixels.
Files can always be read and saved, but compressed pixel data cannot
easily be modified.


## License

pydicom has an <a href="https://github.com/pydicom/pydicom/blob/master/license.txt" target="_blank">MIT-based license.


## Installing

If you haven't installed it yet, see our [installation instructions](/pydicom-install)


## Using pydicom
Once installed, the package can be imported at a python command line or used
in your own python program:

```python
import pydicom
```

See the <a href="https://github.com/pydicom/pydicom/tree/master/pydicom/examples" target="_blank">examples directory</a> Also see the <a href="/pydicom-user-guide">Pydicom User Guide</a> for more details of how to use the package.

## Where to go from here?

 - [Visualization with Pydicom](/pydicom-visualization)


## Support

Please join the <a href="http://groups.google.com/group/pydicom">pydicom discussion group</a> to ask questions or give feedback. Bugs can be submitted through the <a href="https://github.com/pydicom/pydicom/issues" target="_blank">issue tracker</a> on Github. Besides the example directory, cookbook recipes are encouraged to be posted on the <a href="https://github.com/pydicom/pydicom/wiki" target="_blank">wiki page</a>.

New versions, major bug fixes, etc. will also be announced through the group, and posted on this site.


## Next Steps

To start learning how to use pydicom, see the <a href="/pydicom-getting-started">Getting Started Guide.</a>

[^1]: For DICOM network capabilities, see the <a href="https://github.com/patmun/pynetdicom" target="_blank">pynetdicom</a> and <a href="https://github.com/scaramallion/pynetdicom3" target="_blank">pynetdicom3</a> projects.
