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

After getting the car running, my priority was addressing the fact that the car came with a single key. I'm prone to putting things in places that are so secure even I can never find them again, and I didn't want that to happen to the VW.

Unfortunately, certain Mk4 VWs — I think post-2000, but don't quote me on that — have an immobilizer that makes it impossible to simply have a new key cut. While a duplicate key will start the car, it will immediately shut down and greet the prospective pilot with a dreaded glyph:

![Immo3 light in a Mk4 gauge cluster.](assets/img/mk4-key-coding/immo3.jpg)

If you see this light, the immobilizer has kicked in and you're not going anywhere until you get a transponder coded (or "adapted") to work with the car.

There are a few tools that can do this, but they're quite expensive or require Windows or only work for a certain number of cars or have other obnoxious restrictions. Considering this software cost more than the $200 I paid for the car, I looked for more frugal options. Call me parsitonyous.

I don't blame you if you stop reading now.

## Enter kw1281test

After a bit of searching, I came across an open source tool called [kw1281test](https://github.com/gmenounos/kw1281test). It's a brilliant little utility that can use dumb — and cheap! — KKL cables to talk to older VAG ECUs.

Documentation is sparse and, unlike the paid tools, kw1281test is command-line only. Still, it's quite powerful! Most everything you'll read from here down I've already added to the [kw1281test wiki](https://github.com/gmenounos/kw1281test/wiki). If you want clear, concise, prosaic, and IMHO boring directions, check out the wiki. If you want a fuller, bordering on prolix, explanation, you've come to the right place!

## Parts & tools

1. A laptop (or desktop _very_ close to your VW). I did this on a Mac, but it should also work on Linux and Windows (with some slight tweaks outlined in the [wiki](https://github.com/gmenounos/kw1281test/wiki)).
2. A USB -> KKL cable. Most of the cheap ones have a CH340 chip that will only work on Windows. If you plan to use a Mac or Linux, you'll need one with an FTDI chipset, like [this one](https://www.amazon.com/dp/B0BFDYC4SK). Honestly, just buy an FTDI cable because it works on Windows too.
3. A USB-A to USB-C adapter (optional)

