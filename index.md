---
title: Pydicom
keywords: containers,dicom,python
sidebar: main_sidebar
permalink: index.html
toc: false
---


[![Gitter chat](https://badges.gitter.im/pydicom.png)](https://gitter.im/pydicom/Lobby)

Dicom (Digital Imaging in Medicine) is the bread and butter of medical image datasets, storage and transfer. This is the future home of the Pydicom documentation. If you are a Python developer looking to get started with Dicom and Python, this will be the place to learn and contribute! For now, here are some helpful links, and general plan for some of the code bases in the organization. If you want to come and chat, find our community on Gitter, or post an issue on one of our repos.

## Modules

### Pydicom
If you want to work with dicom datasets, you should use [pydicom](https://github.com/pydicom/pydicom). We have started a base of docs here, and see the <a href="https://pydicom.github.io/pydicom" target="_blank">documentation</a> for you to get started.

### Pynetdicom
[pynetdicom3](https://github.com/pydicom/pynetdicom3) is where you want to start if you want to create Service Class Providers (SCPs) or Service Class Users (SCUs). These are the little servers/processes that echo/store/move/find dicom datasets around. This is the bread and butter of the protocol, and is based on the original [pynetdicom](https://github.com/patmun/pynetdicom). We will soon be consolidating these two so that it is less confusing.

### Deid
[deid](https://pydicom.github.io/deid) is a simple module and client that can handle coding (replacement of identifiers) with a study alias. See the [documentation](https://pydicom.github.io/deid) base for getting started.


## Applications
[sendit](https://pydicom.github.io/sendit) is an example Dockerized web application to recive Dicom images, deidentify using your API (and deid, above), and then send off to different storage locations. This application is under development, and not yet ready for use. See the [documentation](https://pydicom.github.io/sendit) for details.

[dicom-database](https://pydicom.github.io/dicom-database) is a simlpified version of sendit, intended for local management of DICOM. This application is under development.


## Containers
We will be developing different dicom applications that are container-based. This means using [Docker](https://docs.docker.com/get-started/) and [Singularity](https://singularityware.github.io) to easily deploy servers (more suited for Docker), and general tools and applications (Singularity is more suited for tools on shared resources).

### Getting Started Containers
[Dicom-Containers](https://github.com/pydicom/dicom-containers) serves equivalent Singularity and Docker containers for working with dicom tools and pydicom. Specifically:

 - [getting-started](https://github.com/pydicom/dicom-containers/tree/master/getting-started) serves a [Docker](https://hub.docker.com/r/pydicom/dicom/) and [Singularity](https://singularity-hub.org/containers/1861/) container,each of which is a "quick start" image that you can build to easily start using some basic tools for working with dicom files. Currently, the image installs the [Dicom ToolKit](http://support.dcmtk.org/docs/), along with miniconda3 installed with pydicom and pynetdicom3.
 - [pydicom-docs](https://github.com/pydicom/dicom-containers/tree/master/pydicom-docs) is a container that builds sphinx docs, intended for developers of pydicom that want a solution to develop docs that doesn't require installing additional dependencies.

### Dicom Scraper
[Dicom Scraper](https://github.com/pydicom/dicom-scraper) is a tool under development to detect burned-in pixel annotations with ORC, and remove them. Currently, the Dockerized application is using an older version of scipy and python 2*, and this will be updated. The detection is working relatively good and will still need some testing and tweaking.


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
