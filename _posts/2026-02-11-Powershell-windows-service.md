---
layout: post
title: "PowerShell - Check Windows Service Status"
categories: PowerShell
author:
- John Case
---

PowerShell offers simple ways to perform administrative tasks such as checking the status of a service. This can be combined with an if statement to act on a stopped service automatically. These commands can be incorporated into a much larger script to check multiple services.
The first step is to store the service name in the variable $ServiceName. Then you can use another variable to store the service information which contains the status information. The Get-Service command can be used to retrieve this information.
Then, using an if statement, you can compare the service info status to a static value. In the example, the service info status is checked against the value Running which determines whether is started and running. The actions can then be taken on the service such as starting it or alerting the appropriate parties. In the example, the script attempts to start the service, then performs a refresh of the service information and writes the new status to the console log.

{% highlight powershell %}
<!-- {% raw %} -->
$ServiceName = ‘Service’
$ServiceInfo = Get-Service -Name $ServiceName
if ($ServiceInfo.Status -ne ‘Running’) {
write-host ‘service is not started, starting service’
Start-Service -Name $ServiceName -verbose
$ServiceInfo.Refresh()
write-host $ServiceInfo.Status
}
write-host ‘all done’
<!-- {% endraw %} -->
{% endhighlight %}
