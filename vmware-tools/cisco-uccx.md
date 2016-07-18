#Cisco UCCX VMware Tools Upgrade
## Cisco UCCX Console
* Login Cisco UCCX console
* Change UCCX OS security mode to permissive mode

<pre>
admin:<b>utils os secure status</b>
OS Security status:             enabled
Current mode:                   enforcing
</pre>
<pre>
admin:<b>utils os secure permissive</b>
OS security mode change to Permissive
</pre>

<pre>
admin:<b>utils os secure status</b>
OS Security status:             enabled
Current mode:                   permissive
</pre>

## VMware vSphere
* Login VMware vSphere client
* Right click on UCCX virtual machine. Navigate `Guest > Install/Upgrade VMware Tools` menu
* Select `Interactive Tools Upgrade` option
* Click `OK` button

## Cisco UCCX Console
* Login Cisco UCCX console
* Upgrade VMware tools

<pre>
admin:<b>utils vmtools status</b>

VMware Tools are out-of-date. Please run "utils vmtools upgrade"
</pre>

<pre>
admin:<b>utils vmtools upgrade</b>

***   W A R N I N G   ***
Running this command will update your current version of VMware Tools
to the latest version prescribed by the ESXi host on which this VM is
running. The tools install will cause your system to reboot twice.

Continue (y/n)?<b>y</b>
</pre>

* Wait until UCCX completes reboot process
