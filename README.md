# <img src="https://static.sidefx.com/images/apple-touch-icon.png" width="25" height="25" alt="Hbuild Logo"> Houdini-Docker
![Autobuild](https://github.com/aaronsmithtv/houdini-docker/actions/workflows/houdocker_autobuild.yml/badge.svg)
[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-HQbuild-f06c00?logo=docker)](https://hub.docker.com/r/apostolistriantafyllou/hqbuild)
![Docker Pulls](https://img.shields.io/docker/pulls/apostolistriantafyllou/hqbuild)

## Hqueue Production Build Docker Image

Houdini-Docker is a project that automatically builds and pushes Docker images for the latest production build of SideFX Houdini. This project ensures you always have an up-to-date Docker image for Houdini, making it easier to create and deploy containerized environments for your 3D graphics projects.

*Note: All Hbuild images are currently built with linux_x86_64 production builds. To build an image with an alternate instruction set, see the [hinstall README](hinstall/README.md).*

---

**Why choose Houdini-Docker?**
- Houdini-Docker offers a trustworthy source of Houdini installation images for security-conscious studios. All workflow runs are publicly visible for transparency.
- Images generated by Houdini-Docker are approximately 65% smaller than the most popular Houdini installation images, saving storage space and improving deployment speed.
- Keep up-to-date with the latest production builds within your Dockerfile, without the need for executing pipeline scripts.
- Simplify the installation process by eliminating standard manual download and install workflows.

---

Whether you're new to Python, Docker, or Houdini, this README aims to provide you with friendly, helpful, and informative instructions to get you started with Hbuild.

## Table of Contents

- [Using Hbuild Images](#using-hbuild-images)
- [Features](#features)
- [Contributing](#contributing)
- [License](#license)

## Using Hbuild Images

If you want to get started quickly with using Houdini-Docker images, follow these simple steps:

1. Ensure you have [Docker](https://www.docker.com/products/docker-desktop) installed on your system. 

2. Open a terminal (Command Prompt, PowerShell, or Terminal, depending on your operating system).

3. Pull the most recently generated Houdini image by running the following command:
    ```shell
    docker pull aaronsmithtv/hbuild:latest
    ```
4. To create and run a container from the pulled image, execute the following command:
    ```shell
    docker run -it --name houdini-container aaronsmithtv/hbuild:latest
    ```

5. Now, you can use Houdini within the container by running the appropriate command for your desired Houdini application, with a default `PATH` environment variable configured to allowing you to launch processes such as `hserver`, `hython`, or `sesinetd`.

6. When you're finished, exit the container by typing `exit` and pressing Enter.

For an example process on how to launch a test `hserver` instance (to verify your remote license server can be contacted), see the [hinstall README](hinstall/README.md).

## Features

- Automatically checks for the latest Houdini production build every day at midnight.
- Builds a Docker image with the latest Houdini build.
- Pushes the new image to Docker Hub with the build tag and as the latest image.

## Contributing

We welcome contributions to the Houdini-Docker project! If you'd like to contribute, please follow these steps:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Submit a pull request.

For any questions or discussions, please open an issue or contact me whenever!

## License

This project is released under the [MIT License](LICENSE).

All Hbuild or Houdini-Docker generated Docker images are built and distributed with and under the terms of their specified Houdini [*End User License Agreement (EULA)*](https://www.sidefx.com/legal/license-agreement/) date (as of October 13, 2021). You must be aware of the EULA terms and conditions when using this image. By using this image, you agree to abide by the terms and conditions of the Houdini EULA.
