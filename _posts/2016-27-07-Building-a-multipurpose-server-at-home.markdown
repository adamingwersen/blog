---
layout:     post
title:      "Building a home-server for less than 1500 USD"
subtitle:   "...perhaps a good idea"
date:       2016-07-16
author:     "Adam"
header-img: "img/servernerd.jpg"
tags:		[Server | Hardware | SuperMicro | GPU-Computing]
---

<h3><center> Why would you want to do that? </center></h3>
Well.. Having primarily worked with statistical programming, I think I could learn a lot from getting down-and-dirty with the hardware. Furthermore, for processing big data, I would like a fast computer to interact with from my Lenovo laptop. The server I'm building will be able to expand heavily by adding more than (possibly) 1TB RAM and extra GPU's and dual CPU's.

Also, the server will be used as a storage facility, backup and I will learn to interact with a Linux server from the bottom up. So; here's a list of reasons that I want to build my own server:

<ul style="list-style-type:circle">
 <li><h6> Have extra computing power and storage</h6></li>
 <li><h6> Play with GPU computing </h6></li>
 <li><h6> Learn Linux Server building</h6></li>
 <li><h6> Practise and set-up with different data-base tools</h6></li>
 <li><h6> Learning about hardware</a></li>
</ul>

Accepting that I could probably do something which would be a lot easier if I just wanted extra storage and computing power - I also see this as a learning process from which I will develop a lot of useful knowledge. 

The budget for the server is set to 10.000 DKK ~ $1478 US. 

<h3><center> The Hardware </center></h3>

Before setting out the get the hardware, I had to learn a bit about my needs and the compatibility of different parts. As with most DIY computer-projects, you start with selecting an appropriate motherboard:

<h4><center> Picking a Motherboard </center></h4>

Having considered my needs, I decided that I wanted a motherboard which allowed for heavy expansion. For a start, I wanted to be able to fit in 2 CPU's. 

Having studied a couple of blog-posts, I decided on a manufacturer for a Dual-Socket Motherboard. [Supermicro](https://www.supermicro.nl/index.cfm) appeared to be one of the better suppliers of such a product. Starting out, I utilized a [Motherboard Selector Tool](http://mbsa.supermicro.com/mbsa/), provided by Supermicro. I wanted a X10 structure in a E-ATX format that would fit into a 4U/Tower chassis with at least 2 x16 PCIE Slots. From here, the selector narrowed down my possibilites to about 10 different "mobo's". I did not care for as many as 7 PCIE x16 slots, and did not have any need for Audio, nor SAS3. I eventually decided on the [X10DRi](http://www.supermicro.com/products/motherboard/xeon/c600/x10dri.cfm), which cost $407 US on amazon. 

It has the following specs, as hihglighted by Supermicro

1. Dual socket R3 (LGA 2011) supports
    Intel® Xeon® processor E5-2600
    v4†/ v3 family; QPI up to 9.6GT/s
2. Intel® C612 chipset
3. Up to 2TB† ECC 3DS LRDIMM , up to
    DDR4- 2400†MHz ; 16x DIMM slots
4. 3 PCI-E 3.0 x16 and 3 PCI-E 3.0 x8
5. Intel® X540 Dual port 10GBase-T
6. 10x SATA3 (6Gbps); RAID 0, 1, 5, 10
7. Integrated IPMI 2.0 and KVM with
    Dedicated LAN
8. 5x USB 3.0 (2 rear, 2 via header, 1 Type A), 6x USB 2.0 (2 rear, 4 via header)



![The Motherboard](img/supermicro_x10DRi_mobo.jpg)



<h4><center> Picking a CPU </center></h4>

In selecting a CPU for the X10DRi, I focused primarily on Intel Processors. I wanted a compatible processor below $500 US, and would prefer an 8-cores-or-more  Broadwell processor. The motherboard's socket allowed for a R3 LGA2011, Intel Xeon E5 2600-series v3/v4 CPU.

I decided to go with a v4 model as I wanted 2133 TM/s RAM-speed. As mentioned before, I wanted to get a low-end Xeon CPU below $500 US in the Intel 2600-series. Therefore, my choiced were limited to the following:

|CPU||Cores/Threads|Operating Speed|Cache|Price|
|---|:------------:|--------------:|----:|----:|
|E5-2609 v4 |8/8 |1.7 GHz|22MB|$306|
|E5-2020 v4 |8/16|3.0 GHz|22MB|$417|
|E5-2023 v4 |8/8 |3.2 GHZ|11MB|$444|









