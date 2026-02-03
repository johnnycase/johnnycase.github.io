---
layout: post
title: "PowerShell - Cast a String as an Integer"
categories: PowerShell
author:
- John Case
---

When numbers are stored as a string in a database, it is difficult to sort them, so they are readable to human users. PowerShell makes this operation simple, to take a string value, cast it as an integer, sort it by numeric value and create an output file with the sorted values.

To perform this operation, use the code here.

{% highlight powershell %} 
$SortValues = Get-Content -Path C:\FilePath\FileName.file | ForEach-Object -Process {[int]$_} | Sort-Object
$SortValues | ForEach-Object {$_.ToString(“0000000000000000”)} | Out-File -FilePath C:\FilePath\SortedFileName.file
{% endhighlight %}
