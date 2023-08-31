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

Units like the one pictured above claim to reduce the 90-104 MHz bands by 14 MHz (to 76-90 MHz) and the 104-108 MHz bands by 28 MHz (to 76-80 MHz).

To make this more concrete, here's how a few LA radio stations would be reduced:

| Station | True Freq | In-car Freq | Format |
|:-------:|:-------:|:-------:|:-------:|
|  KKJZ   |  88.1   |  88.1     | Jazz |
|  KXLU   |  88.9   |  88.9     | College |
|  KCRW   |  89.9   |  89.9     | Public radio |
|  KUSC   |  91.5   |  77.5   | College |
|  KRRL   |  92.3   |  78.3   | Hip-hop |
|  KDAY   |  93.5   |  79.5   | Classic hip-hop |
|  KTWV   |  94.7   |  80.7   | Urban contemporary |
|  KLOS   |  95.5   |  81.5   | Classic rock |
|  KYSR   |  98.7   |  84.6   | Alternative |
|  KIIS   |  102.7  |  88.7   | Top 40 |
|  KBIG   |  104.3  |  76.3   | 90s to now |
|  KPWR   |  105.9  |  77.9   | Hip-hop |
|  KROQ   |  106.7  |  78.7   | Alternative |

## Drawbacks
The main drawback of using a band expander is that we're trying to get a radio that can receive 14 MHz of spectrum to receive 20 MHz of spectrum. In this way, I guess it _technically_ does expand the available FM bands. However, in practice, it's more likely to create frequency collisions that reduce the number of stations you can hear clearly.

For exmaple, based on [Radio Locator](https://radio-locator.com/cgi-bin/locate?select=city&city=Los%20Angeles&state=CA) data, these are all of the potential conflicts in Los Angeles:

| Freq | Station 1 | Station 2 | Conflicting Formats |
|:-------:|:-------:|:-------:|:-------:|
| 76.3 | 90.3 | 104.3 | Spanish/Adult contemporary |
| 76.7 | 90.7 | 104.7 | Public radio/Rhythmic oldies |
| 77.1 | 91.1 | 105.1 | Classical/Country |
| 77.5 | 91.5 | 105.5 | Classical/Regional Mexican |
| 77.9 | 91.9 | 105.9 | Christian/Hip-hop |
| 78.3 | 92.3 | 106.3 | Hip-hop/Asian |
| 79.1 | 93.1 | 107.1 | Adult hits/Spanish hits |
| 79.5 | 93.5 | 107.5 | Classic hip-hop/Spanish hits |
| 88.7 | 88.7 | 102.7 | College/Top 40 |
| 89.9 | 89.9 | 103.9 | Publish radio/Spanish hits |

There are some _very_ popular channels in there, but I suppose it's still much better than having no radio at all.

To determine the potential frequency collisions in your area:
1. Look up the available stations in your Zip code on [Radio Locator](https://radio-locator.com/).
2. Add 14 to each station under 90 MHz to see if there's a conflict (e.g., if your area gets 88.7 and 102.7, you have a conflict because 88.7 + 14 = 102.7).
3. Subtract 14 from each station over 104 MHz to see if there's a conflict (e.g., if your area gets 106.3 and 92.3, you have a conflict because 106.3 - 14 = 92.3).

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

The bit circled in red is the port where your radio antenna plugs in, and it's where we'll insert our band expander.

Fortunately, you should be able to reach this port without removing the head unit. Simply peel back the carpet in the driver's footwell until you can see the antenna cable poking out:

![Picture of driver's side carpet pulled back with the radio antenna cable circled in red.](assets/img/beat-fm-band-expander/carpet-pulled-back.jpg)

You should only need to undo a bit of velcro and get around a single snap. It really doesn't take much. You'll also have fewer wires and obstacles in the way — I have a Japanese electronic toll card installed in this same spot.
