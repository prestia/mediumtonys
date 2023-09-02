---
layout: post
title: "DIY: Coding new keys for Mk4 VWs with Immo3 using open source software"
author: "Medium Tony"
categories: mk4-gti
tags: [mk4-git,diy]
image: mk4-key-coding/key.jpeg
---
## Intro
I bought a 2002 VW GTI 1.8T for $200 in July 2023 to turn into a [24 Hours of Lemons](https://24hoursoflemons.com) car. The car hadn't run in years and was in pretty rough shape, but I got it running — well! — for less than $150 in parts (and an embarrassing number of trips to the local pick-a-part).

After getting the car running, my priority was addressing the fact that I had a single key. I'm prone to putting things in places that are so secure even I can never find them again, and I didn't want that to happen to the VW.

Unfortunately, certain Mk4 VWs — I think post-2000, but don't quote me on that — have an immobilizer that makes it impossible to simply have a new key cut. While a duplicate key will start the car, it will immediately shut down and greet the prospective pilot with the most dreaded of glyphs:

![Immo3 light in a Mk4 gauge cluster.](assets/img/mk4-key-coding/immo3.jpg)

If you see this light, the immobilizer has kicked in and you're not going anywhere until you get a transponder coded (or "adapted") to work with the car.

There are a few tools that can do this, but they're either quite expensive or require Windows or only work for a certain number of cars or have other obnoxious restrictions. Considering this software costs more than the $200 I paid for the car, I looked for more frugal options. Call me parsitonyous.

I don't blame you if you stop reading now.

## Enter kw1281test

After a bit of searching, I came across an open source tool called [kw1281test](https://github.com/gmenounos/kw1281test). It's a brilliant little utility that can use dumb — and cheap! — KKL cables to talk to older VAG ECUs.

Documentation is sparse and, unlike the paid tools, kw1281test is command-line only. Still, it's quite powerful! Most everything you'll read from here down I've already added to the [kw1281test wiki](https://github.com/gmenounos/kw1281test/wiki). If you want clear, concise, prosaic, and IMHO boring directions, check out the wiki. If you want a fuller, bordering on prolix, explanation, you've come to the right place!

## Parts & tools

1. A laptop (or desktop _very_ close to your VW). I did this on a Mac, but it should also work on Linux and Windows (with some slight tweaks outlined in the [wiki](https://github.com/gmenounos/kw1281test/wiki)).
2. A USB -> KKL cable. Most of the cheap ones have a CH340 chip that will only work on Windows. If you plan to use a Mac or Linux, you'll need one with an FTDI chipset, like [this one](https://www.amazon.com/dp/B0BFDYC4SK). Honestly, just buy an FTDI cable because it works on Windows too.
3. A set of _new_ transponders ([this 4-pack](https://www.amazon.com/dp/B098MC82J6?psc=1&ref=ppx_yo2ov_dt_b_product_details) is cheap and works). The transponders _must_ be new. You cannot reuse transponders that have been used with another VW.
4. A USB-A to USB-C adapter (optional)

## Instructions

### Step 1: Install FTDI drivers

I'm going to describe installation on a Mac because that's the primary platform I use. Instructions for Linux are avaiable [here](https://github.com/gmenounos/kw1281test/wiki#linux). If you're on windows, ¯\_(ツ)_/¯.

To use kw1281test on Mac, you'll need to be running macOS 10.4 or higher.

Download the [FTDI drivers](https://ftdichip.com/drivers/d2xx-drivers/) for your platform. Make sure to pay attention to your system architecture (x64 or ARM). Choose x64 if you're on an Intel-based Mac; choose ARM for Macs with Apple silicon (M1, M2, etc.).

Once downloaded, unzip the drivers to your Desktop. This should create a folder called `release`.

The installation process works roughly as follows, but you may need to change the driver version number in steps 4 and 5:

1. Open a Terminal window
2. If the `/usr/local/lib` directory does not exist, create it: `sudo mkdir /usr/local/lib`
3. If the `/usr/local/include` directory does not exist, create it: `sudo mkdir /usr/local/include`
4. Copy the dylib file to `/usr/local/lib`: `sudo cp ~/Desktop/release/build/libftd2xx.1.4.24.dylib /usr/local/lib/libftd2xx.1.4.24.dylib`
5. Make a symbolic link: `sudo ln -sf /usr/local/lib/libftd2xx.1.4.24.dylib /usr/local/lib/libftd2xx.dylib`
6. Copy the D2XX include file: `sudo cp ~/Desktop/release/ftd2xx.h /usr/local/include/ftd2xx.h`
7. Copy the WinTypes include file: `sudo cp ~/Desktop/release/WinTypes.h /usr/local/include/WinTypes.h`
8. Delete the `release` folder from your desktop

### Step 2: Find the serial number of your KKL cable

[stay tuned...]
