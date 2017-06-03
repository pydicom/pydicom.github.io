---
title: Getting Started with Containers
sidebar: containers
permalink: containers
folder: docs
---

{% include toc.html %}

A container is like a packaged, portable environment that you can run on your computer. For the purposes of research computing, this comes down to two big players:

## Docker
Docker is the enterprise, well known linux container, the first one that really changed the world by exposing different parts of the linux kernel via an easy to use API. You can find a lot of containers on <a href="https://hub.docker.com" target="_blank">Docker Hub</a>, and there are many well-known scientific containers along with services (think databases, web servers, job queues) that have all been "Dockerized."  You can read their <a href="https://docs.docker.com/get-started/" target="_blank">getting started guide</a>, or just browse some of the scientific <a href="https://biocontainers.pro/" target="_blank">biocontainers</a> that are driving reproducible science.


## Singularity
Singularity is a linux container that you can run safely and securely on a shared resource. You can read about how it came about as an open source effort in <a href="http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0177459" target="_blank">this paper</a>, or just jump into the <a href="http://singularity.lbl.gov" target="_blank">docs</a>.

We will be building and using both Docker and Singularity images. Docker works really well, but it won't work for you if you aren't the root user, such as on your local research cluster. Singularity can help here.

To get started, let's <a href="/containers-dcmtk">build containers to use dcmtk</a>, a nice set of tools for working with and using dicom images.
