---
layout:     post
title:      "Build a multipurpose Linux server at home for less than $1500"
subtitle:   "Part 1: The Hardware"
date:       2016-07-27
author:     "Adam"
header-img: "img/servertangle.jpg"
tags:		[Server | Hardware | SuperMicro|Linux Server]
---
<h1><center> Part 1: The Hardware </center></h1>

This post is about me building a server. I have never built a computer before and have little experience with computer hardware. Google = Sensei. 

<h2><center> Why would you want to do that? </center></h2>
Well.. Having primarily worked with statistical programming, I think I could learn a lot from getting down-and-dirty with the hardware. Furthermore, for processing big(-ger) data, I would like a fast computer to interact with from my Lenovo laptop. The server I'm building will be able to expand heavily by adding more than (possibly) 512GB RAM and extra GPU's and a singleXeon CPU.

Also, the server will be used as a storage facility, backup and I will learn to interact with a Linux server from the bottom up. So; here's a list of reasons that I want to build my own server:

<ul style="list-style-type:circle">
 <li><h4> Have extra computing power and storage</h4></li>
 <li><h4> Learn Linux Server building</h4></li>
 <li><h4> Practise and set-up with different data-base tools</h4></li>
 <li><h4> Learn about security features of Linux Server</h4></li>
 <li><h4> Learning about hardware</h4></li>
</ul>

Considering that I could probably do something which would be a lot easier if I just wanted extra storage and computing power - I also see this as a learning process from which I will develop a lot of useful knowledge. 

The budget for the server is set to about 10.000 DKK ~ $1478 US. 

Before setting out the get the hardware, I had to learn a bit about my needs and the compatibility of different parts. As with most DIY computer-projects, you start with selecting an appropriate motherboard:

<h2><center> Picking a Motherboard </center></h2>

Having considered my needs, I decided that I wanted a motherboard which allowed for some expansion. For a start, I wanted to be able to fit in one v4 Xeon CPU. 

Having studied a couple of reviews and blog-posts, I decided on a manufacturer for a Uni-Socket Motherboard. [Supermicro](https://www.supermicro.nl/index.cfm) appeared to be one of the better suppliers of such a product. Starting out, I wanted a X10 structure in an ATX format that would fit into a Mid-Tower chassis with at least 2 x16 E-PCI Slots. I wanted a LGA 2011-3 socket-format, which allows for the newer, larger CPU's. Looking around Supermicro's website the options were many, but concidering price - I decided on the X10SRA. 

It has the following specs, as hihglighted by Supermicro


1. Single socket R3 (LGA 2011) supports
    Intel® Xeon® processor E5-2600
    v4†/ v3, E5-1600 v4†/ v3, 5th/4th gen.
    Core i7
2. Intel® C612 chipset
3. Up to 512GB ECC DDR4 2400†MHz 
    LRDIMM or 128GB ECC/non-ECC
    UDIMM (available with Core i7 only);
    8x DIMM slots
4. 4 PCI-E 3.0 x16 (run at 16/16/NA/8
    or 16/8/8/8), 2 PCI-E 2.0 x1 (in x4)
5. Intel® i210-AT Dual port GbE LAN
6. 10x SATA3 (6Gbps)
7. 1x COM, 1x TPM
8. 8x USB 3.0 ports
    (6 rear + 2 via header)
9. HD Audio 7.1 channel connector by
    Realtek ALC1150

<center><img src="https://s3.graphiq.com/sites/default/files/5030/media/images/Super_Micro_X10SRA-F_6526158.jpg"></center>

[Supermicro MBD X10SRA](http://www.supermicro.com/products/motherboard/xeon/c600/x10sra.cfm)

[Price: $271](http://www.newegg.com/Product/Product.aspx?Item=N82E16813182958&ignorebbr=1)

This board allows for 4 PCI-E ports, and has 10 SATA ports as well as 8 DIMM slots. I will not be filling these out in the near future. Also, it provides me with the option of either Xeon E5 1600/2600 series, which means that I can also fit a CPU designed for 2-socket boards on here. 


<h2><center> Picking a CPU </center></h2>

In selecting a CPU for the X10SRA, I focused only on Intel Processors. I wanted a compatible processor below $500 US, and would prefer a 6-cores-or-more  Broadwell processor. The motherboard's socket allowed for a R3 LGA2011, Intel Xeon E5 1600/2600-series v3/v4 CPU.

I decided to go with a v4 model as I wanted 2133 TM/s RAM-speed. As mentioned before, I wanted to get a low-end Xeon CPU below $500 US in the Intel 1600/2600-series. Therefore, my choices were limited to the following:

|CPU       |Cores/Threads|Base   |Turbo   |Cache|Price|
|:--------:|:-----------:|:-----:|:------:|:---:|:---:|
|E5-1620 v4| 4/8 		 |3.5 GHz|3.8 GHz |10MB |$297 |
|E5-1630 v4| 4/8 		 |3.7 GHz|4.0 GHz |10MB |$406 |
|E5-2620 v4| 8/16        |2.1 GHz|3.0 GHz |22MB |$417 |
|E5-2623 v4| 8/8 		 |2.6 GHz|3.2 GHZ |11MB |$444 |

 I used [cpu-world](http://www.cpu-world.com/Compare/406/Intel_Xeon_E5-2620_v4_vs_Intel_Xeon_E5-1620_v4.html) for comparing the CPU's. This site is awesome, as you can adjust the comparison CPU's directly in the URL - although only a 1-by-1 comparison at a time.

 Given the extra threads and the lowest power consumption, i chose the 2620 at a bit higher pricepoint than the 1600's. But with double the cores - and a lower power consumption of 85W compared to 140W.

<center><img src="http://images10.newegg.com/productimage/19-117-629-03.jpg"></center>

[Intel Xeon E5 2620 v4, BX80660E52620V4](http://www.cpu-world.com/CPUs/Xeon/Intel-Xeon%20E5-2620%20v4.html) 

[Price: $435](http://www.newegg.com/Product/ProductList.aspx?Submit=ENE&DEPA=0&Order=BESTMATCH&Description=intel+E5-2620+v4&N=-1&isNodeId=1)

<h2><center> Picking the RAM </center></h2>

Picking RAM is not very difficult. However, when picking RAM for a server-setup one should be aware, that there's something called ECC RAM, which is Error-Correction-Code RAM. Also, server-RAM differs in typically being RDIMM or LRDIMM. I went with the Crucial Brand, as they had an elaborate compatibility guide, [Crucial Advisor Tool](http://www.crucial.com/usa/en/memory-info?cm_re=top-nav-_-flyout-memory-_-us-memory). The processor required the RAM to be, at best 2133 TM/s and DDR4. So i chose accordingly. I went with 2 16GB ECC RDIMM Server RAM Sticks. 

The motherboard has 8 RAM slots, so picking the 2x16GB sticks instead of e.g. 8x4GB sticks allows me to keep these existing RAM when expanding - and not being required to replace any RAM in the near future.

<center><img src="http://images17.newegg.com/is/image/newegg/20-148-840-Z01?$S640$"></center>

[Crucial 32(2 x 16GB) DDR4-2133 ECC RDIMM, CT2K16G4RFD4213](http://eu.crucial.com/eur/en/ct2k16g4rfd4213)

[Price: $170](http://www.newegg.com/Product/Product.aspx?Item=N82E16820148840&ignorebbr=1)

<h2><center> Picking a boot-drive (SSD) </center></h2>

For booting, you obviously want an SSD. I figured, I wanted to install various software on the server, which is why i wanted the comfort of 256GB. It had to be a SATA3 drive and it had to be quite fast. I picked a Samsung 850 PRO 256GB 2,5-Inch Internatl SSD with 550MB/S read and 520MB/S write. This SSD has V-NAND, which, to my knowledge is ideal for more standby time and intended for enterprise-grade usage.

<center><img src="http://images10.newegg.com/productimage/A12K_131111183232863646EctktGWr53.jpg"></center>

[Samsung 850 Pro 256GB, 2.5¨ SATA III](http://www.samsung.com/us/computer/memory-storage/MZ-7KE256BW)

[Price: $135](http://www.newegg.com/Product/Product.aspx?Item=9SIA12K4820044&ignorebbr=1)

<h2><center> Picking a Storage drive (HDD)</center></h2>
I had a 5400 rpm 3TB Western Digital NAS Drive lying around. I figured, I'd use that for a start. 

Here are the specs of the drive:

[WD RED 3TB NAS, WD30EFRX](http://www.newegg.com/Product/Product.aspx?Item=N82E16822236344&cm_re=NAS_WD30EFRX-_-22-236-344-_-Product)

[Price: $109](http://www.newegg.com/Product/Product.aspx?Item=N82E16822236344&cm_re=NAS_WD30EFRX-_-22-236-344-_-Product)

<h2><center> Cooling </center></h2>

As this had to run as a 24/7 Server, I wanted to buy a Cooler/Heatsink for the CPU. I went with one of Noctuas that was LGA2011 E5-2600 compatible. I was initially concerned about the size of the fan and went with the smallest in the NH-series, the NH-D9L. I picked Noctua simply because of the amount of positive reviews about the brand and their supposedly pseudo-silent air-cooling.

I went with air-cooling for this setup instead of liquid-cooling as I was not aiming for overclocking the CPU - also, for simplicity and risk-aversion.

<center><img src="http://images17.newegg.com/is/image/newegg/35-608-068-Z02?$S640$"></center>

[Noctua NH-D9L](http://noctua.at/en/nh-d9l)

[Price: $55](http://www.newegg.com/Product/Product.aspx?Item=N82E16835608068&ignorebbr=1)

<h2><center> Chassis and PSU </center></h2>

Now, there are two major options in terms of selecting a chassis. Either, I choose a chassis with integrated power supply - or I select one, where I need to buy a seperate power supply. 

If I choose the integrated chassis-PSU solution I don't have a lot of options in terms of looks. However the quick-solution provides a tried-and-tested airflow/PSU setup. The cost of a quick-solution is, of course, a bit steeper. 

Studying the requirements for a server specced like this, I realized that I did not need more than 300-500W for a power supply - the power consumption especially matters when building servers. This is because it will be running 24/7 as opposed to a gaming-rig or workstation. 

Supermicro provides a series of mid-tower server chassis' with built-in power supplies and proper airflow. I picked one, that would fit my ATX board and possibly a couple of low-end GPU's.

<center><img src="http://images17.newegg.com/is/image/newegg/11-152-170-Z07?$S640$"></center>

[Supermicro SC732D2-500B](https://www.supermicro.com/products/chassis/tower/732/sc732d2-500.cfm)

[Price: $150](http://www.newegg.com/Product/Product.aspx?Item=N82E16811152170&ignorebbr=1)

<h2><center> RAID </center></h2>

Initially, RAID will not be needed. 

<h2><center> Budget so far </center></h2>

The costs of the components considered thus far. I would like to eventually afford 1 or 2 GPU's but for now this will suffice. Also, the cost of these parts in Denmark is significantly more expensive than on e.g. NewEgg.com. And then there's shipping. 

|Item        |Manufacturer   |Model          |Price in U$D|
|:----------:|:-------------:|:-------------:|:----------:|
|Motherboard |SuperMicro     |X10SRA         |$271        |
|CPU         |Intel          |Xeon E5-2620 v4|$435        |
|RAM         |Crucial        |CT2K16G4RFD4213|$170        |
|SSD         |Samsung        |850 Pro 256GB  |$135        |
|HDD         |Western Digital|3TB RED NAS    |$109        |
|Heatsink    |Noctua         |NH-D9L         |$55         |
|Chassis     |Supermicro     |CS723D2-B500   |$150        |
|            |               |               |            |
|<b>Total</b>|               |               |<b>$1325</b>|


<h2><center> Wait, no GPU's? </center></h2>

For now, no. 

This is because: 

Proper GPU's for parrallel computing such as the enterprise-grade GPU's from NVIDIA: Quadro or Tesla are insanely expensive. Such GPU's are optimized for machine learning tasks and are powering the largest neural networks around the globe. This may indeed be overkill for my "needs".

Obviously, one could aim for lower grade gaming GPU's, which would be well fitted for the sorts of tasks, I would be throwing at my server. 

But GPU's are power-hungry and they get hot. So the setup will require a power supply with higher wattage - and more fans/cooling. For a start, this rack will not be utilizing a GPU until I have at least $800-1000 more to spend.

<h2><center> What now? </center></h2>



The next part of this series will be concerned with assembly of the server and making it run Linux Server.