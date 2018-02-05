---
title: "Getting Started with [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in Docker"
description: "Description of how to get started with [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in Docker"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 01/15/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---


# Getting Started with [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in Docker container
<!-- Should I also mention Microsoft Dynamics NAV 2018? -->
All shipped cumulative updates and all localizations of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] 2016 and 2017 are available as Docker images in the Docker Hub, ready for execution on a Windows system with Docker installed.


> [!NOTE]  
> [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] ships and maintains Docker images for all versions (all cumulative updates, all localizations) since[!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] 2016RTM. No images will be shipped for older versions, but you can run [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] 2015 in Docker. Moreover, with Docker Generic image version 0.0.4.1 you can run older versions in Docker. 


## Steps to run [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in Docker

Go through the following steps to start [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in a Docker container. 

1) Enable virtualization on the host machine that will be hosting the Docker container.
2) Enable Hyper-V and Containers on the machine from Windows Features.
3) Install and configure Docker.
4) Run a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Docker image.

### Enable virtualization 

The first step is to enable virtualization on the host machine. To check if this is already done, go to the **Performance** tab on **Task Manager**. 

### Enable Hyper-V and Containers 

Next, Hyper-V and Containers must be enabled on the host machine that will run the Docker container. You can do this from Windows Features.      


### Install and configure Docker
The first step to installing Docker is choosing the version of Docker that is appropriate for the host operating system. Use Docker for Windows if the host operating system is Windows 10 Professional edition and Docker Enterprise Edition if the host operating system is Windows Server 2016.
Another thing that needs to be known is that Docker is set by default to use Linux Containers. You can change that by pressing right-click on the Docker tray icon and then select **Switch to Windows Containers**. 
After you install Docker, it is required to log out of Windows, to log in again, and then Docker will start running automatically. 


###  Run the Docker image 

Run the following command in a Command Prompt as Administrator to run a Docker image of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]:  
`docker run -e accept_eula=Y -m 4G microsoft/dynamics-nav`

You will get the W1 country version of the latest cumulative update of the latest version of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] running on your computer. You can also run any other cumulative update (of 2016 or 2017), by specifying the version, the CU, and the country version you want as a tag: 

`docker run -e accept_eula=Y -m 4G microsoft/dynamics-nav:2016-cu5-dk`

> [!NOTE]   
> When you execute the docker run command, Docker will start downloading the image if it does not already exist.

At this point, you can open your internet browser and type in the Web Client URL. You will be prompted with a login dialog, where you can login with the NAV Admin Username/Password displayed.

## NAV Container Helper

NAV Container Helper makes it easier to work with NAV Containers on Docker. On a Windows 10 or Windows Server 2016, start Powershell and type:

`install-module navcontainerhelper -force`                       

To see which functions are available in the NAV Container Helper use:

`Write-NavContainerHelperWelcomeText`

## See also:
<!--
// In progress: 
[Troubleshooting NAV on Docker](devenv-troubleshooting-nav-on-docker.md)
// In progress:
[Docker's commands]()
// Should we add the link to the Docker hub?
[](https://hub.docker.com/r/microsoft/dynamics-nav/)

-->