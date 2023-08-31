---
layout: post
title: "DIY: FM band expander install"
author: "Medium Tony"
categories: beat
tags: [beat,diy]
image: beat-fm-band-expander/rav-helper.jpg
---
## Intro
If you're reading this tutorial, it's probably because you were disappointed when your freshly-imported Beat could only tune in to 1 or 2 radio stations. If you're wondering why, it's because your Japanese radio works in the [76-95 MHz band](https://en.wikipedia.org/wiki/FM_broadcasting_in_Japan) and your region probably uses the [87.5/88-108 MHz band](https://en.wikipedia.org/wiki/FM_broadcast_band) for FM radio.

Thankfully, if you have the stock Honda Beat Gathers head unit, there's a relatively simple fix: Install a [band expander](https://en.wikipedia.org/wiki/Band_expander) to tune in to stations above 95 MHz.

The name "band expander" is a bit misleading. The device doesn't allow your radio to tune in to a wider range of stations. Rather, it shifts the frequency of each station by a set amount. Your head unit will still show 76-95 but you'll actually be listening to something 14Mhz (or 28 MHz) higher.

![Picture of the Car Frequency Antenna, Radio FM Band Expander for Japanese Autos.](assets/img/beat-fm-band-expander/band-expander.jpg)

Units like the one pictured above claim to reduce the 90-104 MHz bands by 14 MHz (to 76-90 MHz) and the 104-108 MHz bands by 28 MHz (to 76-80 MHz). This strikes me as odd for two reasons:
1. There's no way to tune in to any stations above 87.5/88 MHz but below 90 MHz; and
2. some of the stations could collide (e.g., 91.4 and 105.4 would both reduce to 77.4).

I've yet to spend any time confirming whether these are genuine problems, but I'll update this post when I do. Some amount of variable conversion makes sense -- after all, the Japanese band is 1 MHz narrower -- but this particular solution seems to introduce a lot of potential collision and _still_ misses 2 MHz of the U.S. FM band.

To make this more concrete, here's how a few LA radio stations would be reduced:

| Station | True Frequency | In-car Frequency | Genre |
|:-------:|:-------:|:-------:|:-------:|
|  KROQ   |  106.7  |  78.7   | Alt. Rock |
|  KLOS   |  95.5   |  81.5   | Rock/AOR |
|  KCRW   |  89.9   |  ??     | NPR member |
|  KPWR   |  105.9  |  77.9   | Hip-hop |
|  KXLU   |  88.9   |  ??     | College |
|  KUSC   |  91.5   |  77.5   | College |
|  KKJZ   |  88.1   |  ??     | Jazz |
|  KTWV   |  94.7   |  80.7   | Adult contemporary |
|  KDAY   |  93.5   |  79.5   | Classic hip-hop |
|  KRRL   |  92.3   |  78.3   | Hip-hop |
|  KBIG   |  104.3  |  76.3   | 90s to now |
|  KIIS   |  102.7  |  88.7   | Pop |

## Parts & tools
1. FM band expander (I bought [this cheap one](https://www.amazon.com/dp/B07TV7MWT1) on Amazon)
2. Multimeter (anything capable of measuring 12v DC will do)
3. 22-18 AWG ring terminal
4. 22-18 AWG quick diconnect
5. Crimp tool
6. 22-18 AWG insulated wire (optional)

## Instructions

### Step 1: Peel back carpet to gain access to antenna connection

The back of your Gathers head unit looks like this:

![Picture of the back of a Honda Beat Gathers head unit with the antenna port circled in red.](assets/img/beat-fm-band-expander/radio-back.jpg)

The bit circled in red is the port where you radio antenna plugs in, and it's where we'll insert our band expander.

Fortunately, you should be able to reach this port without removing the head unit. Simply peel back the carpet in the driver's footwell until you can see the antenna cable poking out:

![Picture of driver's side carpet pulled back with the radio antenna cable circled in red.](assets/img/beat-fm-band-expander/carpet-pulled-back.jpg)
