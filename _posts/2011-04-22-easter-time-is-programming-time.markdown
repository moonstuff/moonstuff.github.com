---
layout: default
title: easter time is programming time
---

nom1 now writes reports!

    $ time zcat ../events-2006-03-01.gz | ./nom1 + + reports.kch
      EOF reached: 20328219 records: 
      454226 searches, 19635314 appearances, 238679 clicks, 1173820 urls
      generating url reports for 1173820 urls

      real  1m50.786s
      user  1m46.600s
      sys   0m27.490s

The reports.kch file ends up being 185MB. That about 3300MB -> 185MB in 2 minutes. Single threaded C actually turned out pretty good!
