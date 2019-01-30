---
layout: post
title: iSCSI bound NICs VMware
---

Ran into a situation where an environment had forcefully (meaning literally ripped the cards out of the server) removed NICs bound to iSCSI in vSphere 6. When attempting to manage iSCSI settings in the iSCSI adapter you would get the following error:
“Call IscsiManager.QueryBoundVnics for object iscsiManager on vCenter Server failed”
Appears this caused some corruption in the iSCSI stack on the host due to the cards suddenly “disappearing” from the system. Pretty easy fix to this one luckily….
1) vMotion everything off this host and put in maintenance mode
2) Copy IQN/Data settings for iSCSI config as will need to re-create
3) Go into iSCSI adapter settings and hit the Disable option
4) Delete contents (3 files) of this directory: /etc/vmware/vmkiscsid/
5) Reboot host
6) After reboot, add a new iSCSI adapter and re-add existing config IQN/Data settings. Also don't forget to bind the adapters as needed/required by your config
