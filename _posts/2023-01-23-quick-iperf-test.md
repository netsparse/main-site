---
layout: post
author: Angel
date: 2023-01-23
title: Quick iperf test
description: Today i'll show you how to do a quick iperf test.
tag: ["homelab", "reference", "networking"] 
category: networking
excerpt_separator: <!--more-->
published: true
---
Just a quick write up showing how to setup a quick iperf test. <!--more--> 

These come in handy when you need them.


### Server Setup

1. Run
```
iperf -s
``` 

This will setup the current host as the _SERVER_, you'll see a similar output as below:

![server](/assets/img/posts-content/2023-01-23/iperf1.png)

Now go over to the client computer and run the steps below.


### Client Setup

2. Run 
```
iperf -c <server to connect to> 
``` 

Replace `<server to connect to>` with the IP address of the server you setup before.

In our example, it is 192.168.2.198. 

![server](/assets/img/posts-content/2023-01-23/iperf2.png)

You'll see the client establish a connection to the server and output the results on the screen.

![server](/assets/img/posts-content/2023-01-23/iperf3.png)

You'll also see the same from the server side.

![server](/assets/img/posts-content/2023-01-23/iperf4.png)

**Done.**

Our results will be shown when test is completed, usually after a few seconds (depending on your network).

### Additional Reference

For any additional commands or reference, check out:

```
iperf --help
```

```
man iperf
```

[ < back ](/blog)
