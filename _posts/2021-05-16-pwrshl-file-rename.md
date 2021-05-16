---
layout: post
title:  "PowerShell — Renaming Files"
date:   2021-05-16 17:24:00 -0500
categories: post
---

Renaming files is a common operation in windows, it’s simple enough to select a file and rename it using the context menu. But what if you have many files or need to automate file renaming? PowerShell reduces this operation to several simple commands with a for each object loop.

{%highlight powershell%}
$filelist = (Get-ChildItem “C:\FilePath\*.*” | foreach-object {$_.name})
foreach ($file in $filelist)
{
$newname = ‘customString’ + $file + ‘.file’
Rename-Item “C:\FilePath\$file” $newname -verbose
clear-variable newname
}
{%endhighlight%}

Begin by searching for the file you want to rename. The **Get-ChildItem** command will find the list of files and pass it to **foreach-object**. This is all stored in the **$filelist** variable. Then a foreach loop is created in which a new file name is given to each file. The **$newname** variable will control how the file is named with the **$file** section being the original file name. This original file name can be replaced with whatever is needed for your circumstance. Dates and times can also be added to the name by using **Get-Date** and formatting the date and time as desired. The new name is then passed to the **Rename-Item** command to perform the rename operation. Finally the newname variable is cleared so it can be used in the next loop.