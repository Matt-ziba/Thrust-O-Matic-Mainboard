---
title: "Thrust-O-Matic Mainboard"
author: "MattyZ"
description: "The electronics portion of Thrust-O-Matic - my rocket motor thrust stand project."
created_at: "2024-06-06"
---

## 17.6.2025 - Start of project
I have experimented in the past with KNSB rocket motors but had no reliable way of measuring their thrust. For that reason, I decided to build a thrust stand. Instead of going with the typical vertical motor orientation seen in most hobbyist solid motor thrust stands, I will use a horizontal setup. While this increases the mechanical complexity of the design, it should allow me to measure both the thrust and the weight of the motor.

I would also like to measure the chamber pressure of the motor using a pressure transducer. The thrust stand will include a wireless ignition system as well.

I have chosen the ESP32-S3-WROOM-1U MCU for its excellent wireless functionality, ample GPIO pins, fast processor (which should providing enough headroom for data logging, BLE, and data acquisition) and the U.FL antenna connector, which allows me to use a much more powerful antenna than the default PCB one on the standard WROOM variant.

For analog-to-digital conversion from the sensors, I decided to use the ADS1220 ADC. It supports two differential inputs, allowing me to connect both the thrust and weight load cells to a single ADC and multiplex between them. This splits the sampling rate between the two channels, but that’s not a major issue since I don’t need high frequency sampling on the weight cell, as weight changes are usually slower and more linear. The plan is to sample the thrust cell at 1800 SPS and the weight cell at around 200 SPS, possibly reducing the rates if needed for accuracy.

A second ADS1220 will be used for the pressure transducer data, or potentially for thermocouple data if required.

As for the sensors, I’ve selected a generic 30 kg, 25 mm inline load cell for thrust measurement, and a 5 kg bar-type load cell for weight. For chamber pressure, I will use an XDB401 pressure transducer, which is rated for up to 5 MPa.

For the accessory ICs, I selected the CP2102 for USB-UART conversion and the IP5306 for battery management. The device will use two separate battery packs: one to power the ESP32 and other peripherals, and another dedicated to the ignition system. The main system battery will be rechargeable via USB, while the ignition battery will need to be charged separately, or possibly through a second battery charger, depending on whether I decide to integrate one.

After a couple hours of research i’ve created a block diagram of the electronics and have started work on the schematic.

#### Block diagram:
![Block Diagram](https://hc-cdn.hel1.your-objectstorage.com/s/v3/ad1050f0f4cdaa7833b0d3583ed547c1f04eebf5_image.png)

## 8.7.2025- Update, finished BMS circuit
It’s been a while since the last update. I have been busy with end of the school year responsibilities and vacation. I’m currently in Poland, but I finally found some time to continue work on the project. Today, I focused on researching and drafting the schematic for the BMS.

The device is designed to charge its onboard battery when connected to USB, but only if the USB source is capable of delivering at least 3A. This functionality hasn’t been fully implemented yet. Initially, I considered using a USB-C PD controller IC to detect whether the connected USB port can supply enough current. However, I eventually decided that a simple switch would be a more simple solution. This way, the device will start to charge only when the charging is manually enabled.

The battery is necessary because the device is intended to operate outdoors where there is no access to mains power. At first, I considered using a power bank, but I eventually went for a dedicated battery instead. It also gives me a chance to better understand battery charging logic and power management.

There is not much else to say, hopefully tomorrow I will have some more time to work on the project.

#### BMS schematic:
![Block Diagram](https://hc-cdn.hel1.your-objectstorage.com/s/v3/0bf70f7e9a7e821279a5e142fa11d75b07970837_image.png)
