---
layout: post
author: Angel
date: 2023-01-16
title: Quick iperf test
description: Today i'll show you how to do a quick iperf test.
tag: ["homelab", "dell"] 
category: homelab
excerpt_separator: <!--more-->
published: false
---
Just a quick write up showing how to setup a quick iperf test. <!--more--> These come in handy when you need them.


### Server

It's generally easier to setup the server side first.

1. Run iperf -s This will setup this host as the SERVER

Now go over to the client computer and run the steps below.
Client

2. Run 
```iperf -c <server to connect to> ``` 
on the client computer, specifying the IP address of the server you setup before, in our example, the IP of the server is 192.168.2.198.

You'll see the client establish a connection to the server and output the results on the screen.

You'll also see the same from the server side.

Done.

Our results will be shown after the test is done, usually taking a few seconds to complete, depending on your network.
Additional Reference

For any additional commands or reference, check out:

```iperf --help```

```man iperf```

[ < back ](/blog)
