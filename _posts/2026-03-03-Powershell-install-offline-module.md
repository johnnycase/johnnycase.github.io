---
layout: post
title: "PowerShell - Install Offline Modules"
categories: PowerShell
author:
- John Case
---

Installing powershell modules is simple, right? Open a powershell window and use the Find-Module cmdlet or if you know the name of the module go straight to Install-Module. This will connect to the PowerShell gallery and download and install the module for you. But what if the computer that needs the new module is not connected to the internet? If you are facing this challenge, you have come to the right place. This guide will take you step-by-step through the process.

Please note that powershell modules are not compatible with every powershell version, remember to check the module prerequisites before installing it on the desired computer.

Prerequisites
Here are the prerequisites you will need to complete the steps in this guide.

A Windows computer, connected to the internet. The name of the powershell module you want to install. The path where you will save the module on your computer.

Installing the Module
The first step for installing a PowerShell module on an offline computer is to download it with a computer that is connected to the internet.

In the Start menu search for the Windows Powershell application and open it.
On the command line type Save-Module -Name ModuleName -Path “FilePath” and Enter to run the command. Remember to replace ModuleName and FilePath with the values needed for your use case.
The module will now be saved into the folder defined in the -Path parameter. Browse to this location in File Explorer.
The next step is to move the module folder to the offline computer and import it into powershell.

Copy the folder you located in step 3 and paste it on the offline computer in the following location, C:\Program Files\WindowsPowerShell\Modules.
On the offline computer, search for Windows PowerShell in the Start menu and open it.
On the command line type Import-Module -Name ModuleName and Enter to run the command. Please note that the name entered on the command line needs to match the folder name copied in step 4.
The module has now been installed on the offline computer, congratulations!
