---
title: Visualizing DICOM images using Pydicom
sidebar: pydicom
permalink: pydicom-visualization
folder: docs
---


## Introduction

pydicom is mainly concerned with getting at the DICOM data elements in files,
but it is often desirable to view pixel data as an image.
There are several options:

  * Use any of the many [DICOM viewer](http://www.dclunie.com/medical-image-faq/html/part8.html#DICOMFileConvertorsAndViewers)
    programs available
  * use pydicom with [matplotlib](http://matplotlib.sourceforge.net)
  * use pydicom with python's stdlib [Tkinter](https://docs.python.org/3.4/library/tkinter.html) module.
  * use pydicom with the [Python Imaging Library (PIL)](http://www.pythonware.com/products/pil/)
  * use pydicom with [wxPython](http://www.wxpython.org/)

## Using pydicom with Matplotlib

Matplotlib is available at <a href="http://matplotlib.sourceforge.net/" target="_blank">http://matplotlib.sourceforge.net</a>. 
It can take 2-d image information from `Dataset.pixel_array` and display it. Here is an example::

```python
>>> import pydicom
>>> import pylab
>>> ds=pydicom.read_file("CT_small.dcm")
>>> pylab.imshow(ds.pixel_array, cmap=pylab.cm.bone)
<matplotlib.image.AxesImage object at 0x0162A530>
>>> pylab.show()
```

Thanks to Roy Keyes for pointing out how to do this.


## Using pydicom with Tkinter

The program [pydicom_Tkinter.py](https://github.com/pydicom/pydicom/blob/master/pydicom/contrib/pydicom_Tkinter.py) in the `contrib` folder demonstrates how to show an image using the
Tkinter graphics system, which comes standard with most python installs. It creates a Tkinter PhotoImage in a Label widget or a user-supplied widget.

## Using pydicom with Python Imaging Library (PIL)

The module [pydicom_PIL.py](https://github.com/pydicom/pydicom/blob/master/pydicom/contrib/pydicom_PIL.py) also in the `contrib` folder uses PIL's `Image.show()` method after creating an Image instance from the pixel data and some basic information about it (bit depth, LUTs, etc)

## Using pydicom with wxPython

The module [imViewer-Simple.py](https://github.com/pydicom/pydicom/blob/master/pydicom/contrib/imViewer_Simple.py) also in the `contrib` folder uses wxPython (also PIL, but it notes that it
may not be strictly necessary) to display an image from a pydicom dataset.
