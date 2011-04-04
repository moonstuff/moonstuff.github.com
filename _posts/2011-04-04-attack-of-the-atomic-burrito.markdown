---
layout: default
title: Attack of the Atomic Burrito 
---

I've just uploaded my work so far on the Atomic Burrito. What it is, essentially, is a simple experiment in data aggregation.

You see, I think way too much about the technical problems in my work. Whatever project I am on I think "What if there was another way to do this?" Right now we are aggregating a ton of data. Atomic Burrito provides an easy data set to try out ideas to do with data aggregation.

The input is simple. Think of it as the log for a search engine. There are three types of events:

1. search events: when someone performs a search.
2. appearance events: when a website is listed in the search results.
3. click events: when someone clicks on a website link.

At first glance the data isn't very interesting. What is interesting is when the data is 1.6 billion records and you want to perform millions of queries against it. Just performing a *wc -l* against 1.6 billion records can take 20 minutes. This is when choices such as languages and data storage platforms actually *mean something*.

So, with the initial toolset done and most of the data generated (about 5 hours to go on derpify) it's time to start on the actual aggregator. There are lots of things that I'd like to try:

* Language comparisons between C, Ruby, Erlang, Clojure and maybe JavaScript.
* Data storage with [KyotoCabinet](http://fallabs.com/kyotocabinet/), [Riak](http://wiki.basho.com/), [Mnesia](http://www.erlang.org/doc/apps/mnesia/index.html) and others.
* Libraries such as [ZeroMQ](http://www.zeromq.org/), [libev](http://software.schmorp.de/pkg/libev.html), [EventMachine](http://rubyeventmachine.com/) and [OTP](http://www.erlang.org/doc/).

But to begin with, I think something simple is in order. I usually strive to make things simpler, believing that the smaller codebases are the easiest to develop and maintain. So my first attempt will be the simplest that I can think of: written in C, single threaded and receiving events on STDIN. It stores the event data in KyotoCabinet and can output simple text file reports for each site.

Wish me luck.
