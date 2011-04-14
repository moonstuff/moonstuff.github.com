---
layout: default
title: nom1 in memory
---

My favourite KyotoCabinet feature is that the database type and tuning can be set just by the filename. Tonight I was playing with "+", which is just std::map from C++. Here is the output:

    EOF reached: 95438437 records
    1924021 searches, 92407706 appearances, 1106709 clicks
      Command being timed: "./nom1 + +"
      User time (seconds): 355.92
      System time (seconds): 8.36
      Percent of CPU this job got: 99%
      Elapsed (wall clock) time (h:mm:ss or m:ss): 6:06.75

That's about a quarter of a million records per second. At about one hundred million records (1/16th data set) I would have started to squeeze for RAM on my machine (8GB) so I quit it. I would like to see performance when it hits swap though, but not tonight.

I also did a little work on nom1, adding another database to store the list of urls received. This is for the next part which I have to write: collating the aggregated statistics into reports on disk. At the moment I think I'll keep to simple text files, one file per month per url.
