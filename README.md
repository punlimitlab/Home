# Home - Run ASP.NET Apps on PI2, Linux and Windows with Docker 
Informations and example with PartsUnlimited ASP.NET web site on how to run ASP.NET on your Raspberry PI or Linux and Windows.

PartsUnlimited [![Build from VSTS](https://img.shields.io/vso/build/punlimit/f0338caf-c189-45e3-bcfa-abdd23fc6e9d/13.svg)](https://punlimit.visualstudio.com/DefaultCollection/_apis/public/build/definitions/f0338caf-c189-45e3-bcfa-abdd23fc6e9d/13/badge)
PI: [![RPI Downloads from Docker Hub](https://img.shields.io/docker/pulls/punlimitlab/rpipunlimit.svg)](https://registry.hub.docker.com/u/punlimitlab/rpipunlimit) Linux: [![Downloads from Docker Hub](https://img.shields.io/docker/pulls/punlimitlab/punlimit.svg)](https://registry.hub.docker.com/u/punlimitlab/punlimit)

Docker ASP.NET Base image  [![Build from VSTS](https://img.shields.io/vso/build/punlimit/f0338caf-c189-45e3-bcfa-abdd23fc6e9d/8.svg)](https://punlimit.visualstudio.com/DefaultCollection/_apis/public/build/definitions/f0338caf-c189-45e3-bcfa-abdd23fc6e9d/8/badge)
[![RPI Downloads from Docker Hub](https://img.shields.io/docker/pulls/punlimitlab/aspnetbase.svg)](https://registry.hub.docker.com/u/punlimitlab/aspnetbase)

## Quick Start
### Pull and run PartsUnlimited ASP.NET website on your Raspberry PI with Docker
You will need to prepare a running docker client and daemon on your Raspberry. Hypriot has ready to use flash card for docker on RPIs.
Once ready,you can run this two commands to run the site and access it on http://YourRaspeberryHost
docker pull punlimit/rpipunlimit
docker run -t -d -p 80:5000 punlimit/rpipunlimit

### Pull and run PartsUnlimited ASP.NET website on Linux with Docker
You can easely prepare a running docker environment with docker Tools. 
docker pull punlimit/rpipunlimit
docker run -t -d -p 80:5001 -e "server.urls=http://*:5001" punlimit/punlimit

### Build and run PartsUnlimited ASP.NET website on Linux with Docker
You will need a Windows Server 2016 CTP machine do try it. You can use the Microsoft quick start a Wincontainer environment compatible with docker. As this thread on Windows Container forum stated, we cannot push windows container image on docker hub. So we will have some extra steps.
1. Build ASP.NET DNX image (our Dockerfile.base.windows. Microsoft has also build one, so you can just pull it)
2. Publish the ASP.NET website (with no runtime or a Windows compatible one)
3. Build the ASP.NET website image from the ASP.NET DNX image. (our Dockerfile.windows)

## You can also access our running PartsUnlimited websites on Docker in Microsoft Azure VMs
Check on the bottom page to see difference on running OS and ASP.NET DNX runtimes.
1. Linux Ubuntu/Mono runtime : http://dockubvm.westeurope.cloudapp.azure.com
2. Windows 10.0/Core Clr 2016 : http://dockwinvm.westeurope.cloudapp.azure.com/

