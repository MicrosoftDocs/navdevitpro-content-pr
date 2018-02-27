---
title: "Running a Container-Based Development Environment"
description: "Description of how to get started with container-based development environment."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/27/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Running a Container-Based Development Environment
Dynamics 365 Business Central is available as a container-based image, ready for execution on a Windows system with Docker installed. The container-based approach is used when you need access to both the AL development environment and the C/SIDE development environment. <!-- more explanation and intro -->

## Prerequisites for running container-based 
Complete the following steps to set up a machine that can run a container-based development environment.

1) Enable virtualization on the host machine that will be hosting the container.  
To check if this is already done, in **Task Manager**, go to the **Performance** tab. 
2) Run the **Windows Features** window, and make sure that **Hyper-V** and **Containers** are enabled on the machine.
3) Install and configure Docker. See the section below.
4) Run ...

### Install and configure Docker
The first step to installing Docker is choosing the version of Docker that is appropriate for the host operating system. 
- Use **Docker for Windows** if the host operating system is **Windows 10 Professional edition**. 
- Use **Docker Enterprise Edition** if the host operating system is **Windows Server 2016**.

By default Docker is set to use Linux containers. Change this by pressing right-click on the Docker tray icon and then select **Switch to Windows Containers**. After you install Docker, you must log out of Windows, then log in again, and Docker will start running automatically. 

### Run the container-based image 
Run the following command in a Command Prompt as Administrator to run a Docker image of Dynamics 365 Business Central:  
`docker run -e accept_eula=Y -m 4G microsoft/dynamics-nav` <!-- this needs to change -->

You will get the W1 country version of the latest <!-- ?--> update of the latest version of Microsoft Dynamics NAV 2016 and 2017 running on your computer. You can also run any other cumulative update (of 2016 or 2017), by specifying the version, the CU, and the country version you want as a tag: 

`docker run -e accept_eula=Y -m 4G microsoft/dynamics-nav:2016-cu5-dk`

> [!NOTE]   
> When you execute the Docker run command, it will start downloading the image if it does not already exist. A container consists of multiple layers, only the needed layers are downloaded.

At this point, you can open your internet browser and type in the Web client URL. You will be prompted with a login dialog, where you can login with the NAV Admin Username/Password displayed.

## The NavContainerHelper module
To support the use of containers, optional PowerShell scripts are available, which support setup of development environments. Use the `NavContainerHelper` to work with containers. On a Windows 10 or Windows Server 2016, start Powershell as an Administrator and type:

`install-module navcontainerhelper -force`                       

To see which functions are available in the `NavContainerHelper` module use the following command:

`Write-NavContainerHelperWelcomeText`

To quickly get started, run the following command from the `NavContainerHelper` module:

```new-navcontainer -accept_eula -containerName test -imageName microsoft/dynamics-nav:devpreview```

The `NavContainerHelper` will create a folder on the `C:\` drive called DEMO and will place all files underneath that folder. The DEMO folder will be shared to the container for transfer of files etc. If you do not specify a username and a password, it will ask for your password and use the current Windows username. If you specify your windows password, the container setup will use Windows Authentication integrated with the host. The `NavContainerHelper` will also create shortcuts on the desktop for the Dynamics 365 Business Central Web client, a container prompt, and a container PowerShell prompt.

The `navcontainerhelper` module also allows you to add the `-includeCSide` switch in order to add the Dynamics 365 Business Central Windows client and C/SIDE to the desktop and export all objects to a folder underneath C:\DEMO\Extensions for the object handling functions from the module to work.

## See Also