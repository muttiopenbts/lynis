# lynis for Junos OS

## Purpose
Provide a version of Lynis that has been configured and tested on Juniper Network's Junos OS. Junos OS is the FreeBSD flavor of Juniper's OS.

## Junos Specific 
junos.prf has been customized with certain checks disabled or enabled, depending on maturity of testing.  
New tests have been added in the form of plugins.  

## Requirements
* Juniper network device, such as an MX router
* Firmware running Junos OS (not Junos OS Evolved)

## Running
* ```$ git clone <this repo>```
* ```$ tar -zcvf lynis.tgz lynis```
* ```$ scp lynis.tgz root@my-junos-device:/root```
* 
  ```
  $ ssh root@my-junos-device
  root@my-junos-device:~/ # tar -zxvf /root/lynis.tgz ; chown -R 0:0 lynis ; cd lynis
  root@my-junos-device:~/lynis # sh ./lynis --profile junos.prf --plugindir ./plugins audit system
  ```

  ## TODO
  * Further expand plugins to conduct deeper vulnerability analysis.  
    *  E.g. (s|g)uid checks for dangerous or poor coding practices. Check out https://gtfobins.github.io/
    * Shell scripts with poor coding practices.
