# QODM
An unofficial, experimental QGIS Plugin to process UAV Data using the power of OpenDroneMap.

This tool represents a graphical user interface to the commandline tool of OpenDroneMap (see [ODM website](https://www.opendronemap.org/odm/)) running in a local docker environment.

:information_source: Software is currently only tested on Windows 10 version 2004 (inluding WSL 2). Linux support should (with some tweaks) be given.

## Installation Guide

### 1. Docker

OpenDroneMap runs docker. Depending on your operating system, make sure to download the right version and follow the detailed installation guide on following pages:

| Operating System          | Installation Guide                                               |
| ------------------------- | ---------------------------------------------------------------- |
| Windows 10 Pro/Enterprise | https://docs.docker.com/docker-for-windows/install/              |
| Windows 10 Home           | https://docs.docker.com/docker-for-windows/install-windows-home/ |
| Mac                       | https://docs.docker.com/docker-for-mac/install/                  |

Note, that for Windows 10 Home, a working WSL 2 (Windows subsystem for Linux) must be set up.
You can check, if docker is properly installed by using following command in the command prompt of your choice:

```
docker --version
```

### 2. QGIS Settings

In order to make Docker Desktop accessible from QGIS a few configuration steps are required.
Since QGIS overrides the PATH variable at every startup, docker hast to be added to the QGIS PATH variable manually.

Therefore open QGIS and navigate to *Settings > Options > System*.

In the Environment pane further down, check the box to use custom variables and click the plus sign.
For 'apply', set *'Overwrite'*, for 'variable' set *'PATH'* and concatenate the path to your docker binaries to the existing path variables (see Screenshot). Make sure to include separators.

![QGIS Settings](img/qgis_path.png)

### 3. QODM Plugin

