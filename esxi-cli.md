# VMware ESXi Command Line Interface

## Power on VM

```bash
vim-cmd vmsvc/getallvms
vim-cmd vmsvc/power.getstate <vmid>
vim-cmd vmsvc/power.on <vmid>
```

## Migrating VMkernel interface between standard vSwitches

```bash
# esxcfg-vmknic -l
# esxcfg-vmknic -d Port_Group_Name
# esxcfg-vswitch –A "Port_Group_Name" vSwitch0
# esxcfg-vmknic -a -i x.x.x.x -n y.y.y.y Port_Group_Name
```

## Change standard vSwitch name

```bash
vi /etc/vmware/esx.conf
```

## Set cron

```bash
vi /var/spool/cron/crontabs/root

*/5 * * * * vim-cmd vmsvc/power.on 1

kill -HUP $(cat /var/run/crond.pid)
/usr/lib/vmware/busybox/bin/busybox crond
```

