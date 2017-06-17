---
title: Pydicom
keywords: containers,dicom,python
sidebar: main_sidebar
permalink: index.html
toc: false
---

Dicom (Digital Imaging in Medicine) is the bread and butter of medical image datasets, storage and transfer. This is the future home of the Pydicom documentation. If you are a Python developer looking to get started with Dicom and Python, this will be the place to learn and contribute! For now, here are some helpful links, and general plan for some of the code bases in the organization.

## Python Modules

### Pydicom
If you want to work with dicom datasets, you should use [pydicom](/pydicom-introduction). We have started a base of docs here, and see the docs on <a href="https://pydicom.readthedocs.io/en/stable/" target="_blank">readthedocs</a> for you to get started.

### Pynetdicom
[pynetdicom3](https://github.com/scaramallion/pynetdicom3) is where you want to start if you want to create Service Class Providers (SCPs) or Service Class Users (SCUs). These are the little servers/processes that echo/store/move/find dicom datasets around. This is the bread and butter of the protocol, and is based on the original [pynetdicom](https://github.com/patmun/pynetdicom). We will hopefully consolidate these two so that it is less confusing.

### Deid
[deid](https://pydicom.github.io/deid) is a simple module and client that can handle coding (replacement of identifiers) with a study alias. See the [documentation](https://pydicom.github.io/deid) base for getting started.


## Applications
[sendit](https://pydicom.github.io/sendit) is an example Dockerized web application to recive Dicom images, deidentify using your API (and deid, above), and then send off to different storage locations. This application is under development, and not yet ready for use. See the [documentation](https://pydicom.github.io/sendit) for details.


## Containers
We will be developing different dicom applications that are container-based. This means using [Docker](https://docs.docker.com/get-started/) and [Singularity](https://singularityware.github.io) to easily deploy servers (more suited for Docker), and general tools and applications (Singularity is more suited for tools on shared resources).

### Singularity Dicom
[Singularity Dicom](https://github.com/pydicom/singularity-dicom) This will be a "quick start" image that you can build to easily start using some basic tools for working with dicom files. Currently, the image just installs the [Dicom ToolKit](http://support.dcmtk.org/docs/).

## APIs

### Dicom Cookies
As a new person to Dicom, I found it hard to find and programatically download a quick (and maybe fun?) Dicom dataset. Toward this goal, I created a statically served [Dicom Cookies](https://github.com/pydicom/dicom-cookies) dataset. The human readable entrypoint is [here](https://pydicom.github.io/dicom-cookies/), and you can see it being used programatically [here](https://asciinema.org/a/122503?speed=3).

## Coming Soon
We will be creating a set of web application (Dockerized) to be deployed in different cloudy places to work with Dicom. If you are interested in this, please join the effort!

<hr style="margin-top:20px">

<div class="row">
  {% assign loopcount = 1 %}
  {% for post in site.posts %}

   {% if loopcount < 4 %}

   <!-- Parse news-->
   {% if post.category == "news" %}
   {% assign loopcount = loopcount | plus: 1 %}
   <div class="col-md-4">
      <h2><a class="post-link" href="{{ post.url | remove: "/" }}">{{ post.title }}</a></h2>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <p>{{ post.content | truncatewords: 20 | strip_html }}</p>  
   </div>
   {% endif %}

   {% if post.category == "releases" %}
   {% assign loopcount = loopcount | plus: 1 %}
   <div class="col-md-4">
      <h2><a class="post-link" href="{{ post.url | remove: "/" }}">{{ post.title }}</a></h2>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <p>{{ post.content | truncatewords: 20 | strip_html }}</p>  
   </div>
   {% endif %}
   {% endif %}

  {% endfor %}
</div>
