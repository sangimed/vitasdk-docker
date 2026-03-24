[![Docker Pulls](https://img.shields.io/docker/pulls/gnuton/vitasdk-docker.svg)](https://hub.docker.com/r/gnuton/vitasdk-docker)
[![CircleCI](https://circleci.com/gh/gnuton/vitasdk-docker/tree/master.svg?style=svg)](https://circleci.com/gh/gnuton/vitasdk-docker/tree/master)

♡ Vita SDK in a Docker Image ♡
==============================
Daily Vita SDK Docker images.

Features
--------
* Image based on Ubuntu 22.04
* Always with latest stable CMake
* Docker images are built every night at midnight
* Versioned Nightlies
* Tested on popular CI/CD environments (Travis/CircleCI/Azure/...)

Why should I use PSVita SDK Docker images?
-----------------------------------------------
Building PS Vita apps in a Docker container has several advantages:
 - More reliable - A consistent build environment. You can run it in Travis CI, CircleCI, or on your local machine.
 - Faster - Installing VitaSDK for every build is time-consuming.
 - Hassle-free - Do not spend time setting up a working environment. All you need to build your PS Vita app is this image.
 
Quick start
---------------
1. <b>Build a local project with Docker</b>
    Linux/macOS (bash):
    ```bash
    cd your-vita-project
    docker run -v "$PWD:/build/git" -it --rm gnuton/vitasdk-docker
    ```

    Windows PowerShell:
    ```powershell
    cd C:\path\to\your-vita-project
    docker run -v "${PWD}:/build/git" -it --rm gnuton/vitasdk-docker
    ```

    Windows CMD:
    ```bat
    cd C:\path\to\your-vita-project
    docker run -v "%cd%:/build/git" -it --rm gnuton/vitasdk-docker
    ```

    This downloads the latest PSVita SDK Docker image, mounts your local project directory in the container, and lets you build from there.
2. <b>Travis CI</b>
   Do you have a PS Vita project on GitHub? Look at this [simple template](https://github.com/gnuton/vitasdk-docker-testapp-trevis) or fork it if it is a new project.
3. <b>Azure Pipelines</b> Here is a [sample](https://github.com/devnoname120/vhbb/blob/master/azure-pipelines.yml)
4. <b>Circle CI</b> TODO

Versioned Nightlies
----------------------
Every day at midnight, CI scripts build a fresh Docker image with the latest VitaSDK snapshot.
If you want to always build against the latest cutting-edge VitaSDK code, use the gnuton/vitasdk-docker:<b>latest</b> image.
Otherwise, you can pin a specific image version (for example, gnuton/vitasdk-docker:<b>20190626</b> for the 2019-06-26 snapshot).
The list of available image versions is available [here](https://cloud.docker.com/repository/registry-1.docker.io/gnuton/vitasdk-docker/tags).

Build the image
--------------------
If you really want to make changes to the Dockerfile and build it locally, run:
```bash
docker build -t vitasdk-docker .
``` 

Windows PowerShell or CMD:
```powershell
docker build -t vitasdk-docker .
```
