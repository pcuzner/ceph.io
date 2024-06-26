---
title: "v0.80.8 Firefly released"
date: "2015-01-14"
author: "sage"
tags:
  - "release"
  - "firefly"
---

This is a long-awaited bugfix release for firefly. It several imporant (but relatively rare) OSD peering fixes, performance issues when snapshots are trimmed, several RGW fixes, a paxos corner case fix, and some packaging updates.

We recommend that all users for v0.80.x firefly upgrade when it is convenient to do so.

### NOTABLE CHANGES

- build: remove stack-execute bit from assembled code sections (#10114 Dan Mick)
- ceph-disk: fix dmcrypt key permissions (#9785 Loic Dachary)
- ceph-disk: fix keyring location (#9653 Loic Dachary)
- ceph-disk: make partition checks more robust (#9721 #9665 Loic Dachary)
- ceph: cleanly shut down librados context on shutdown (#8797 Dan Mick)
- common: add $cctid config metavariable (#6228 Adam Crume)
- crush: align rule and ruleset ids (#9675 Xiaoxi Chen)
- crush: fix negative weight bug during create\_or\_move\_item (#9998 Pawel Sadowski)
- crush: fix potential buffer overflow in erasure rules (#9492 Johnu George)
- debian: fix python-ceph -> ceph file movement (Sage Weil)
- libcephfs,ceph-fuse: fix flush tid wraparound bug (#9869 Greg Farnum, Yan, Zheng)
- libcephfs: close fd befure umount (#10415 Yan, Zheng)
- librados: fix crash from C API when read timeout is enabled (#9582 Sage Weil)
- librados: handle reply race with pool deletion (#10372 Sage Weil)
- librbd: cap memory utilization for read requests (Jason Dillaman)
- librbd: do not close a closed parent image on failure (#10030 Jason Dillaman)
- librbd: fix diff tests (#10002 Josh Durgin)
- librbd: protect list\_children from invalid pools (#10123 Jason Dillaman)
- make check improvemens (Loic Dachary)
- mds: fix ctime updates (#9514 Greg Farnum)
- mds: fix journal import tool (#10025 John Spray)
- mds: fix rare NULL deref in cap flush handler (Greg Farnum)
- mds: handle unknown lock messages (Yan, Zheng)
- mds: store backtrace for straydir (Yan, Zheng)
- mon: abort startup if disk is full (#9502 Joao Eduardo Luis)
- mon: add paxos instrumentation (Sage Weil)
- mon: fix double-free in rare OSD startup path (Sage Weil)
- mon: fix osdmap trimming (#9987 Sage Weil)
- mon: fix paxos corner cases (#9301 #9053 Sage Weil)
- osd: cancel callback on blacklisted watchers (#8315 Samuel Just)
- osd: cleanly abort set-alloc-hint operations during upgrade (#9419 David Zafman)
- osd: clear rollback PG metadata on PG deletion (#9293 Samuel Just)
- osd: do not abort deep scrub if hinfo is missing (#10018 Loic Dachary)
- osd: erasure-code regression tests (Loic Dachary)
- osd: fix distro metadata reporting for SUSE (#8654 Danny Al-Gaaf)
- osd: fix full OSD checks during backfill (#9574 Samuel Just)
- osd: fix ioprio parsing (#9677 Loic Dachary)
- osd: fix journal direct-io shutdown (#9073 Mark Kirkwood, Ma Jianpeng, Somnath Roy)
- osd: fix journal dump (Ma Jianpeng)
- osd: fix occasional stall during peering or activation (Sage Weil)
- osd: fix past\_interval display bug (#9752 Loic Dachary)
- osd: fix rare crash triggered by admin socket dump\_ops\_in\_filght (#9916 Dong Lei)
- osd: fix snap trimming performance issues (#9487 #9113 Samuel Just, Sage Weil, Dan van der Ster, Florian Haas)
- osd: fix snapdir handling on cache eviction (#8629 Sage Weil)
- osd: handle map gaps in map advance code (Sage Weil)
- osd: handle undefined CRUSH results in interval check (#9718 Samuel Just)
- osd: include shard in JSON dump of ghobject (#10063 Loic Dachary)
- osd: make backfill reservation denial handling more robust (#9626 Samuel Just)
- osd: make misdirected op checks handle EC + primary affinity (#9835 Samuel Just, Sage Weil)
- osd: mount XFS with inode64 by default (Sage Weil)
- osd: other misc bugs (#9821 #9875 Samuel Just)
- rgw: add .log to default log path (#9353 Alexandre Marangone)
- rgw: clean up fcgi request context (#10194 Yehuda Sadeh)
- rgw: convet header underscores to dashes (#9206 Yehuda Sadeh)
- rgw: copy object data if copy target is in different pool (#9039 Yehuda Sadeh)
- rgw: don’t try to authenticate CORS peflight request (#8718 Robert Hubbard, Yehuda Sadeh)
- rgw: fix civetweb URL decoding (#8621 Yehuda Sadeh)
- rgw: fix hash calculation during PUT (Yehuda Sadeh)
- rgw: fix misc bugs (#9089 #9201 Yehuda Sadeh)
- rgw: fix object tail test (#9226 Sylvain Munaut, Yehuda Sadeh)
- rgw: make sysvinit script run rgw under systemd context as needed (#10125 Loic Dachary)
- rgw: separate civetweb log from rgw log (Yehuda Sadeh)
- rgw: set length for keystone token validations (#7796 Mark Kirkwood, Yehuda Sadeh)
- rgw: subuser creation fixes (#8587 Yehuda Sadeh)
- rpm: misc packaging improvements (Sandon Van Ness, Dan Mick, Erik Logthenberg, Boris Ranto)
- rpm: use standard udev rules for CentOS7/RHEL7 (#9747 Loic Dachary)

### GETTING CEPH

- Git at [git://github.com/ceph/ceph.git](http://github.com/ceph/ceph)
- Tarball at [http://ceph.com/download/ceph-0.80.8.tar.gz](http://ceph.com/download/ceph-0.80.8.tar.gz)
- For packages, see [http://ceph.com/docs/master/install/get-packages](http://ceph.com/docs/master/install/get-packages)
- For ceph-deploy, see [http://ceph.com/docs/master/install/install-ceph-deploy](http://ceph.com/docs/master/install/install-ceph-deploy)
