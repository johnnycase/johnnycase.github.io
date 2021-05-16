---
layout: post
title:  "Powershell — Compare File Length"
date:   2021-05-12 10:12:00 -0500
categories: post
---

After a file copy is complete, how can you be sure the entire file was copied? This can be done with the file length command in PowerShell. This will compare the length in bytes of each file and, combined with an if statement, is a way to perform remediation on a failed file copy automatically.

{%highlight powershell%}
$file1 = Get-Item ‘C:\FilePath\File1.file’ -Verbose
$file2 = Get-Item ‘C:\FilePath\File2.file’ -Verbose
If ($file1.Length -eq $file2.Length)
{ Write-Host “File Sizes Match” }
else
{ Write-Host “File Sizes Do Not Match” }
{%endhighlight%}

First, store each file contents in memory using variables and the **Get-Item** command. Then compare them with an if statement using the **file.Length** command. The space in the else rackets can be used to take appropriate action if the file lengths do not match.