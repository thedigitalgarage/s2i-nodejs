NodeJS Docker images
====================

This repository contains the source for building various versions of
the Node.JS application as a reproducible Docker image using
[source-to-image](https://github.com/openshift/source-to-image).

The resulting image can be run using [Docker](http://docker.io).

For more information about using these images with Digital Garage, please see the
official [Digital Garage Documentation](http://docs.thedigitalgarage.io/using_images/s2i_images/nodejs.html).


Versions
---------------
Node.JS versions currently provided are:
* nodejs-0.10
* nodejs-4.8.3
* nodejs-5.12.0
* nodejs-6.10.3 lts
* nodejs-7.10.0
* nodejs-8.0.0 current

Installation
---------------
To build a Node.JS image:

    This image is available on DockerHub. To download it run:

    ```
    $ docker pull thedigitalgarage/s2i-nodejs:8..0.0
    ```

    To build a Node.JS image from scratch run:

    ```
    $ git clone https://github.com/thedigitalgarage/s2i-nodejs.git
    $ cd s2i-nodejs
    $ make build VERSION=8.0.0
    ```

**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of Node.JS.**


Usage
---------------------------------

For information about usage of Dockerfile for NodeJS 0.10,
see [usage documentation](8.x/README.md).


Test
---------------------
This repository also provides a [S2I](https://github.com/openshift/source-to-image) test framework,
which launches tests to check functionality of a simple Node.JS application built on top of the s2i-nodejs image.

Users can choose between testing a Node.JS test application based on a RHEL or CentOS image.

    ```
    $ cd s2i-nodejs
    $ make test VERSION=8.0.0
    ```

**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of Node.JS.**


Repository organization
------------------------
* **`<nodejs-version>`**

    Dockerfile and scripts to build container images from.

* **`hack/`**

    Folder containing scripts which are responsible for the build and test actions performed by the `Makefile`.
