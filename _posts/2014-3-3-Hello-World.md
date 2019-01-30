---
layout: post
title: 2012R2 on ML350p G8
---

#### Notes when deploying Windows Server 2012R2 on HP ML350p Gen 8
Must use Intelligent provisioning (IP) ver 1.6 to be able to deploy win server 2012 r2. Version 2 and above as does not support server– manually flash system board IP by creating bootable USB with correct IP version
[HP USB key utility](https://href.li/?http://h20564.www2.hpe.com/hpsc/swd/public/detail?swItemId=MTX_948972949139480992fcb5b558)
Had to manually update P420i smart array firmware from V1.8 by using 2015 bootable ProLiant SPP as IP couldn’t update a version as old as V1.8 and 2012R2 couldn’t see smart array running V1.8, just stuck on booting screen loop
