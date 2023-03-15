# mg2x

A minimal firmware for OTA (over the air) flashing various target firmwares
starting from Mongoose OS.

Original repository at https://github.com/yaourdt/mgos-to-tasmota. This repository
is tailored to use Tasmota Latest Release Version only.

## Overview

Mg2x is an intermediate firmware that can be used to install [Tasmota](https://github.com/arendst/Tasmota)
on various Shelly models. It will install the latest released version, and you
can continue from there to your favourite target release.

## Install

**Warning:** _This application should generally be safe to use for all supported
devices. Still, overwriting a device's boot loader via OTA update is a risky
operation. If something unexpected fails, your device may be bricked, unless you
know how to flash a new firmware over a wired connection._

**Warning:** _You can go back to Mongoose OS via OTA as well, using [this firmware](https://github.com/yaourdt/tasmota-to-mgos),
but be aware the application is still at an early stage. If something fails,
your device may be bricked, if you don't know how to flash a new firmware over
a wired connection._

Before flashing this firmware, connect your device to a WIFI network with
internet access. From your browser, open the update URL for your device from the
table below. Replace `shellyip` with the IP address of your Shelly. The device
will restart one or two times and attempt to download Tasmota. If this download
succeeds, the device will restart again, and you will see a new WIFI network
labeled _tasmota-????_. This process should take no longer than 4 - 5 minutes,
depending on your network connection.

There is a [video tutorial](https://youtu.be/_oRr8FZyyQ0) on how to flash this
firmware. Thank you, [digiblur](https://github.com/digiblur)!

If the download fails, or your internet connection is disrupted, simply turn the
device off and on again, the intermediate firmware will retry until it succeeds.

In the unlikely event that the WIFI credentials are wrong, the device will try
to connect to a backup WIFI with SSID _mgos-recover_ and password _RJoPuKC3u5_,
which you can use for recovery.

Device | Update URL | Tasmota Template
--- | --- | ---
Shelly 1        | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-Shelly1.zip`       | `{"NAME":"Shelly 1","GPIO":[1,1,0,1,224,192,0,0,0,0,0,0,0,0],"FLAG":0,"BASE":46}`
Shelly 1PM      | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-Shelly1PM.zip`     | `{"NAME":"Shelly 1PM","GPIO":[320,0,0,0,192,2720,0,0,0,0,0,224,0,4736],"FLAG":0,"BASE":18}`
Shelly 1L       | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-Shelly1L.zip`      | `{"NAME":"Shelly 1L","GPIO":[320,0,0,0,192,224,0,0,0,0,193,0,0,4736],"FLAG":0,"BASE":18}`
Shelly Plug S   | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyPlugS.zip`   | `{"NAME":"Shelly Plug S","GPIO":[320,1,576,1,1,2720,0,0,2624,32,2656,224,1,4736],"FLAG":0,"BASE":45}`
Shelly 2        | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-Shelly2.zip`       | `{"NAME":"Shelly 2","GPIO":[0,2752,0,2784,224,225,0,0,160,0,161,2816,0,0],"FLAG":0,"BASE":47}`
Shelly 2.5      | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-Shelly25.zip`      | `{"NAME":"Shelly 2.5","GPIO":[320,0,0,0,224,193,0,0,640,192,608,225,3456,4736],"FLAG":0,"BASE":18}`
Shelly RGBW2    | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyRGBW2.zip`   | `{"NAME":"Shelly RGBW2","GPIO":[0,0,288,0,419,1,0,0,416,32,418,417,0,0],"FLAG":0,"BASE":18}`
Shelly Dimmer 1 | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyDimmer1.zip` | `{"NAME":"Shelly Dimmer 1","GPIO":[0,3200,0,3232,5568,5600,0,0,192,0,193,288,0,4736],"FLAG":0,"BASE":18}`
Shelly Dimmer 2 | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyDimmer2.zip` | `{"NAME":"Shelly Dimmer 2","GPIO":[0,3200,0,3232,5568,5600,0,0,193,0,192,0,320,4736],"FLAG":0,"BASE":18}`
Shelly EM       | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyEM.zip`      | `{"NAME":"Shelly EM","GPIO":[0,0,0,0,0,0,0,0,640,3457,608,224,8832,1],"FLAG":0,"BASE":18}`
Shelly Bulb     | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyBulb.zip`    | **not yet available, only flash if you a perfectly certain about what you are doing**
Shelly Vintage  | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyVintage.zip` | `{"NAME":"Shelly Vintage","GPIO":[0,0,0,0,416,0,0,0,0,0,0,0,0,0],"FLAG":0,"BASE":18}`
Shelly Plug US  | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyPlugUS.zip`  | `{"NAME":"Shelly Plug US","GPIO":[288,0,321,0,224,2720,0,0,2624,32,2656,544,0,0],"FLAG":0,"BASE":45}`
Shelly Duo      | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyBulbDuo.zip` | `{"NAME":"Shelly Duo","GPIO":[0,0,0,0,417,416,0,0,0,0,0,0,0],"FLAG":0,"BASE":18}`
Shelly H&T      | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyHT.zip`      | **not yet available, only flash if you a perfectly certain about what you are doing**
Shelly i3       | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyI3.zip`      | `{"NAME":"Shelly i3","GPIO":[0,0,0,0,0,320,0,0,193,194,192,0,0,4736],"FLAG":0,"BASE":18}`
Shelly Plug 2   | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyPlug2.zip`   | **not yet available, only flash if you a perfectly certain about what you are doing**
Shelly Uni      | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyUni.zip`     | `{"NAME":"Shelly Uni","GPIO":[320,0,0,0,225,1216,0,0,192,193,194,224,0,4864],"FLAG":0,"BASE":18}`
Shelly Duo RGBW | `http://shellyip/ota?url=http://ota.tasmota.com/tasmota/shelly/mg2tasmota-ShellyDuoRGBW.zip` | `{"NAME":"Shelly Duo RGBW","GPIO":[0,0,0,0,0,419,0,0,417,416,418,0,0,0],"FLAG":0,"BASE":18}`


For your convenience, the table above also lists the matching Tasmota device
templates from [templates.blakadder.com](https://templates.blakadder.com) which
you can use to configure Tasmota after installation.

## Build the firmware yourself

You can compile a binary version of this firmware using [mos tools](https://mongoose-os.com/docs/mongoose-os/quickstart/setup.md#1-download-and-install-mos-tool). Once installed, clone this repository and run
`mos build --build-var MODEL=Shelly1 --build-var TARGETFW=tasmota --platform esp8266`
to create a binary for e.g. a Shelly1 switch located in `build/fw.zip`.

## Acknowledgments
Thanks to [rojer](https://github.com/rojer) for helping me with the debugging of
the initial code.

This firmware is build using a fork of [Mongoose OS docker action](https://github.com/dea82/mongoose-os-action)
which can be found [here](https://github.com/yaourdt/mongoose-os-action).
