#Cisco UCCX VMware Tools Upgrade
## Cisco UCCX Console
* Login Cisco UCCX console
* Change UCCX OS security mode to permissive mode
```
admin:utils os secure status
OS Security status:             enabled
Current mode:                   enforcing

admin:utils os secure permissive
OS security mode change to Permissive

admin:utils os secure status
OS Security status:             enabled
Current mode:                   permissive

admin:
```
## VMware vSphere
* Login VMware vSphere client
* Right click on UCCX virtual machine. Navigate `Guest > Install/Upgrade VMware Tools` menu
* Select `Interactive Tools Upgrade` option
* Click `OK` button

## Cisco UCCX Console
* Login Cisco UCCX console
* Upgrade VMware tools
```
admin:utils vmtools status

VMware Tools are out-of-date. Please run "utils vmtools upgrade"

admin:utils vmtools upgrade

***   W A R N I N G   ***
Running this command will update your current version of VMware Tools
to the latest version prescribed by the ESXi host on which this VM is
running. The tools install will cause your system to reboot twice.

Continue (y/n)?y
```
* Wait until UCCX completes reboot process
