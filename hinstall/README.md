# <img src="https://static.sidefx.com/images/apple-touch-icon.png"  width="25" height="25" alt=""> Hbuild
[![HQbuild GitHub Repository](https://img.shields.io/badge/GitHub-Houdini--Docker-f06c00?style=flat-square&logo=github)](https://github.com/apostolistriantafyllou/hqueue-docker)
 ![Docker Pulls](https://img.shields.io/docker/pulls/apostolistriantafyllou/hqbuild)

HQbuild is the repository HQueue-Docker generated images. The images are based on debian:11-slim. HQbuild provides a dockerized installation of HQueue Server, a powerful Batch Job software by SideFX; You can use this image to run HQueue Server in a containerized environment, making it easy to set up and manage.


## Table of Contents

- [Image Tags](#image-tags)
- [Usage](#usage)
- [Quick Start](#quick-start)
- [Support](#support)
- [SideFX EULA](#sidefx-eula)

## Image Tags

- `apostolistriantafyllou/hqbuild:20.0.*-base`
- `apostolistriantafyllou/hqbuild:latest`

## Usage

To run a container with the latest HQbuild Houdini image, use the following command:

```shell
docker run -p 5000:5000 --name hqueueserver apostolistriantafyllou/hqbuild:latest
```

## Contributing
Contributions to this project are welcome! Please feel free to submit a pull request or open an issue on the [Houdini-Docker GitHub repository](https://github.com/aaronsmithtv/houdini-docker).

## SideFX EULA
All Hbuild Docker images are built and distributed with and under the terms of the specified Houdini [*End User License Agreement (EULA)*](https://www.sidefx.com/legal/license-agreement/) date (as of October 13, 2021). You must be aware of the EULA terms and conditions when using this image. By using this image, you agree to abide by the terms and conditions of the Houdini EULA.
