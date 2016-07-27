---
layout:     post
title:      "Building a home-server for less than 1500 USD"
subtitle:   "...perhaps a good idea"
date:       2016-07-27
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
 <li><h6> Learning about hardware</h6></li>
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



![The Motherboard](http://imagescdn.tweaktown.com/content/6/7/6780_04_supermicro_x10dri_t_intel_c612_server_motherboard_review.jpg)



<h4><center> Picking a CPU </center></h4>

In selecting a CPU for the X10DRi, I focused primarily on Intel Processors. I wanted a compatible processor below $500 US, and would prefer an 8-cores-or-more  Broadwell processor. The motherboard's socket allowed for a R3 LGA2011, Intel Xeon E5 2600-series v3/v4 CPU.

I decided to go with a v4 model as I wanted 2133 TM/s RAM-speed. As mentioned before, I wanted to get a low-end Xeon CPU below $500 US in the Intel 2600-series. Therefore, my choiced were limited to the following:

|CPU       |Cores/Threads|Operating Speed|Cache|Price|
|:--------:|:-----------:|:-------------:|:---:|:---:|
|E5-2609 v4| 8/8 		 |1.7 GHz        |22MB |$306 |
|E5-2620 v4| 8/16        |3.0 GHz        |22MB |$417 |
|E5-2623 v4| 8/8 		 |3.2 GHZ        |11MB |$444 |

I figured, I would not get a 1.7GHz processer, if I was to use the server as an at-home-powerhouse. So the 2620 and 2623 were the last contenders. I used [cpu-world](http://www.cpu-world.com/Compare/406/Intel_Xeon_E5-2620_v4_vs_Intel_Xeon_E5-2623_v4.html) for comparing the CPU's. Given the extra threads and the lower price, i chose the 2620 at $417 US in retail. 

<h4><center> Picking the RAM </center></h4>

Picking RAM is not very difficult. However, when picking RAM for a server-setup one should be aware, that there's something called ECC RAM, which is Error-Correction-Code RAM. Also, server-RAM differs in typically being RDIMM or LRDIMM. I went with the Crucial Brand, as they had an elaborate compatibility guide, [Crucual Advisor Tool](http://www.crucial.com/usa/en/memory-info?cm_re=top-nav-_-flyout-memory-_-us-memory). The processor required the RAM to be, at best 2133 TM/s and DDR4. So i chose accordingly. I went with 2 16GB ECC RDIMM Server RAM Sticks. 

The motherboard has 8 RAM slots, so picking the 2x16GB sticks instead of e.g. 8x4GB sticks allows me to keep the existing RAM when expanding.

<img align="center" src="http://static.nix.ru/autocatalog/memory_modules_Crucial/198657_3159_draft_large.jpg" rotate="90">


<h4><center> Picking a boot-drive (SSD) </center></h4>

For booting, you obviously want an SSD. I figured, I wanted to install various software on the server, which is why i wanted the comfort of 256GB. It had to be a SATA3 drive and it had to be quite fast. I picked a Samsung 950 PRO 256GB 2,5-Inch Internatl SSD with 2200MB/S read and 900MB/S write.

![SSD](http://cdn.pcpartpicker.com/static/forever/images/product/c3080e7c05ad8abee6ca41fea18545dd.256c.jpg)

<h4><center> Picking a Storage drive (HDD)</center></h4>
I had a 5400 rpm 3TB Western Digital NAS Drive lying around. I figured, I'd use that for a start. 

<h4><center> Cooling </center></h4>

<h5> A Heatsink </h5>

As this had to run as a 24/7 Server, i wanted to buy a Heatsink for the CPU. I went with one of Intel's that was LGA2011 E5-2600  Compatible. 

![Heatsink](https://images-na.ssl-images-amazon.com/images/I/41hrUePQipL.jpg)

This heatsink requires that the CPU does not exceed 130W and that the chassis is 2U or larger.

<h5> Fansss </h5>

Maybe...

<h4><center> Chassis </center></h4>

Now, there are two major options in terms of selecting a chassis. Either, I choose a chassis with integrated power supply - or I select one, where I need to buy a seperate power supply. 

If I choose the integrated chassis-PSU solution I don't have a lot of options in terms of looks. However the quick-solution provides a tried-and-tested airflow/PSU setup. The cost of a quick-solution is, of course, a bit steeper. 

Having looked at solutions from SuperMicro, which appear nice, I found out that a lot of these require extra fans and are a lot pricier than other options. 

I will probably go with a generic 4U E-ATX rackable server chassis, like this one - and build it into a cupboard or closet.

![Chassis](https://images-na.ssl-images-amazon.com/images/I/41VpsoO5pzL.jpg)

<h4><center> Power Supply </center></h4>

In picking a power-supply for a server, some prefer one with a battery in case of a power outage. I live in Denmark; haven't ever experienced such a thing - and as such, I wont prioritize a battery feature. 

I did however need a power supply with a lot of watts if I am to install GPU's on the mobo and it would have to fit with my chassis and E-ATX format. 

We need one with Gold standard, 750W+, silent and below $150 US.

I hit up a bunch of top-20 lists for PSU's and found one that fitted my needs.

At $100 US, the [Corsair RM750x](http://www.newegg.com/Product/Product.aspx?Item=N82E16817139142&nm_mc=AFC-C8Junction&cm_mmc=AFC-C8Junction-VigLink2-_-na-_-na-_-na&cm_sp=&AID=10446076&PID=3821802&SID=ir4rcyl0rq0035wt00053) seemed like an appropriate choice. 

<h4><center> GPU? </center></h4>

<h4><center> Cables and RAID </center></h4>

<h4><center> Budget as we go </center></h4>

|Item|Manufacturer|Model|Price in U$D|
|:--:|:----------:|:---:|:----------:|
|Motherboard|SuperMicro|X10DRi|$407|
|CPU|Intel|Xeon E5-2620 v4|$435|
|RAM|Crucial|CT2K16G4RFD4213|$170|
|SSD|Samsung|950 Pro|$190|
|HDD|Western Digital|3TB RED NAS|$109|
|Heatsink|Intel|BXSTS200C|$45|
|PSU|Corsair|RM750x|$100|
|Chassis|Rosewill|8-Bays E-ATX 4U|$90|
|GPU|Nvidia|???|???|
|Cabling|Assorted|...|$50-$70|
|||||
|Total|...|...|$1606|

...So, already we're over the budget...








 



















