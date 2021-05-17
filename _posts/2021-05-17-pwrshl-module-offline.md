---
layout: post
title:  "How To Install PowerShell Modules on an Offline Computer"
date:   2021-05-17 11:00:00 -0500
categories: post
---

Installing powershell modules is simple, right? Open a powershell window and use the [Find-Module](https://docs.microsoft.com/en-us/powershell/module/powershellget/find-module?view=powershell-7.1) cmdlet or if you know the name of the module go straight to [Install-Module](https://docs.microsoft.com/en-us/powershell/module/powershellget/install-module?view=powershell-7.1). This will connect to the [powershell gallery](https://www.powershellgallery.com/) and download and install the module for you. But what if the computer that needs the new module is not connected to the internet? If you are facing this challenge, you have come to the right place. This guide will take you step-by-step through the process.

Please note that powershell modules are not compatible with every powershell version, remember to check the module prerequisites before installing it on the desired computer.

## Prerequisites
Here are the prerequisites you will need to complete the steps in this guide.
- A Windows computer, connected to the internet.
- The name of the powershell module you want to install.
- The path where you will save the module on your computer.

## Installing the Module

The first step for installing a powershell module on an offline computer is to download it with a computer that is connected to the internet.
1. In the Start menu search for the **Windows Powershell** application and open it.
2. On the command line type **Save-Module -Name ModuleName -Path "FilePath"** and Enter to run the command. Remember to replace ModuleName and FilePath with the values needed for your use case.
3. The module will now be saved into the folder defined in the **-Path** parameter. Browse to this location in File Explorer.

The next step is to move the module folder to the offline computer and import it into powershell.
4. Copy the folder you located in step 3 and paste it on the offline computer in the following location, **C:\Program Files\WindowsPowerShell\Modules**.
5. On the offline computer, search for Windows PowerShell in the Start menu and open it.
6. On the command line type **Import-Module -Name ModuleName** and Enter to run the command. Please note that the name entered on the command line needs to match the folder name copied in step 4.

The module has now been installed on the offline computer, congratulations!