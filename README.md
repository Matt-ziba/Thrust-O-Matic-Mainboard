# Thrust-O-Matic-Mainboard
### The electronics part of Thrust-O-Matic, my self designed rocket motor thrust stand.

Thrust-O-Matic is a larger project that i have been working on for a while now. It is a rocket motor thrust stand, basically a device which measures the thrust of a rocket motor. I have already made one version in the past, but that one sucked from a mechanical and electronics standpoint so im remaking it, and highway is the perfect opportunity to remake the mainboard.    
The previous mainboard mainly sucked as it used the HX711 ADC, which is not very precise and can only measure at a rate of 40SPS. Thus, the new one uses the ADS1220 24bit ADC, which can measure at up to 2000SPS. The new mainboard also includes an integrated power system, whereas the old one was powered from a powerbank. There are also some other new features, such as a builtin ignition system, the new MCU has a connector for an external antenna and is also way more powerful. This mainboard is also capable of taking in more than a single input, allowing me to measure from 2 loadcells, one for the thrust and one for the weight of the motor, allowing me to get thrust-weight data. Aside from being able to read data from 2 loadcells, it can also read data from a pressure transducer or from a thermocouple, allowing for even more useful data from the motor test. 

I decided to start working on a thrust stand after having some fun with homemade rocket motors. Ive always been a fan of space and thought that building my own motors and eventually rockets would be a cool way to learn some new things and maybe even expand my portfolio.
I have learned a lot from just this one mainboard, too much to write it all out but i think this single project taught me more than an entire year of electronics classes at my high school :D.

This is a picture of the old thrust stand, i unfortunately dont have a photo of the old mainboard as it was assembled on a perfboard and desoldered after i found out that it was garbage.
![old thrust stand](https://hc-cdn.hel1.your-objectstorage.com/s/v3/ae0e8bdd0c780d0fc52b63db5fc21e555bb107a2__6834904f-97b1-41bf-aac8-9e7f33345997_.png)

I decided to focus mainly on the electronics for now, the mechanical still works, so i would like to test out the new mainboard with the stand as it is right not, and make adjustments if necessary.

## Here are pictures of the new mainboard:
#### Schematic:
![Block diagram](https://hc-cdn.hel1.your-objectstorage.com/s/v3/4b502bc708e1614828be4b232de070ce74f9b96d_block_diagram.png)
![Main page](https://hc-cdn.hel1.your-objectstorage.com/s/v3/60cdd45455bd58645dfdf74b1b526ae63e55e011_main.png)
![Power circuitry](https://hc-cdn.hel1.your-objectstorage.com/s/v3/d6586d132afe4d29a1d983518da83fb4230b0e9e_power.png)
![ADS1220](https://hc-cdn.hel1.your-objectstorage.com/s/v3/3fec5f4a6a08f49980534a8b6b5413debc64ff9b_ads1220.png)
![CP2102N](https://hc-cdn.hel1.your-objectstorage.com/s/v3/8633352242ec5d8324485c9245d4cbfaf0765b22_cp2102n-usb-uart.png)
#### PCB:
![PCB with traces](https://hc-cdn.hel1.your-objectstorage.com/s/v3/ea1b65845fff8ced3dd19381e23f711a569c062f_pcb_pcb_tom-v2-mainboard_2025-08-01.png)
![Top of PCB](https://hc-cdn.hel1.your-objectstorage.com/s/v3/64164418b17455f1309fc3230a8da3806a8d95ab__643faf9b-2b64-47f4-80fe-64063634651a_.png)
![Bottom of PCB](https://hc-cdn.hel1.your-objectstorage.com/s/v3/51434b93a5403e2a916ccb267e0ea6e692266f19__e497413a-f775-4170-831a-1d38b79d7c98_.png)
#### 3D models:
![Mainboard 3D model screenshot](https://hc-cdn.hel1.your-objectstorage.com/s/v3/d47cf0837bba7d3b9cd2c3ce79ec2b9803197f51__a5b85fed-d504-4bf3-8373-a334b7def38a_.png)

## BOM:

| ID  | Name                       | Type                    | Quantity | Supplier    | Unit Price | Price per pack |
|-----|----------------------------|-------------------------|----------|-------------|------------|----------------|
| 1   | BH-18650                  | Battery holder          | 2        | LCSC        | 1.24       | 2.24           |
| 2   | 10nF                      | Capacitor               | 11       | LCSC        | 0.024      | 0.22           |
| 3   | 100nF                     | Capacitor               | 18       | LCSC        | 0.243      | 0.27           |
| 4   | 22uF                      | Capacitor               | 8        | LCSC        | 0.36       | 0.45           |
| 5   | 4.7uF                     | Capacitor               | 2        | LCSC        | 0.068      | 0.34           |
| 6   | 1uF                       | Capacitor               | 3        | LCSC        | 0.06       | 0.2            |
| 7   | 6.8uF                     | Capacitor               | 1        | LCSC        | 0.053      | 0.53           |
| 8   | 10uF                      | Capacitor               | 8        | LCSC        | 0.272      | 0.34           |
| 10  | USBLC6-2SC6               | ESD protection IC       | 1        | LCSC        | 0.111      | 0.55           |
| 11  | 1uH                       | Inductor                | 1        | LCSC        | 0.915      | 0.915          |
| 12  | 33Ω                       | Ferrite bead            | 2        | LCSC        | 0.08       | 0.8            |
| 13  | 4.7uH                     | Inductor                | 1        | LCSC        | 1.034      | 1.034          |
| 14  | SOC-R                     | LED                     | 1        | LCSC        | 0.021      | 0.31           |
| 15  | SOC-G                     | LED                     | 3        | LCSC        | 0.023      | 0.43           |
| 18  | XL-3216SURC               | LED                     | 3        | LCSC        | 0.064      | 0.42           |
| 19  | XL-3216SURUGC             | LED                     | 1        | LCSC        | 0.009      | 0.67           |
| 21  | IPP096N03LGHKSA1          | MOSFET                  | 1        | LCSC        | 0.364      | 0.364          |
| 22  | L8050QLT1G                | Transistor              | 5        | LCSC        | 0.037      | 0.73           |
| 23  | 1K                        | Resistor                | 6        | LCSC        | 0.022      | 0.36           |
| 24  | 10K                       | Resistor                | 18       | LCSC        | 0.054      | 0.31           |
| 25  | 100R                      | Resistor                | 11       | LCSC        | 0.03       | 0.28           |
| 26  | 47R                       | Resistor                | 14       | LCSC        | 0.035      | 0.25           |
| 27  | 2R                        | Resistor                | 2        | LCSC        | 0.008      | 0.38           |
| 28  | 1M                        | Resistor                | 1        | LCSC        | 0.002      | 0.21           |
| 29  | 5.1K                      | Resistor                | 2        | LCSC        | 0.006      | 0.29           |
| 30  | 0.25                      | Resistor                | 1        | LCSC        | 0.005      | 0.23           |
| 33  | 100K                      | Resistor                | 2        | LCSC        | 0.12       | 0.59           |
| 34  | 36R                       | Resistor                | 2        | LCSC        | 0.006      | 0.29           |
| 35  | 330R                      | Resistor                | 1        | LCSC        | 0.003      | 0.29           |
| 37  | RJHSE5384                 | RJ45 connector          | 3        | LCSC        | 1.531      | 1.531          |
| 39  | DB127V-5.0-2P-BK-S        | Screw terminal          | 1        | LCSC        | 0.193      | 0.85           |
| 40  | ESP32-S3-WROOM-1U-N16R8   | MCU                     | 1        | LCSC        | 5.665      | 5.66           |
| 41  | SK6812MINI-E              | LED                     | 2        | LCSC        | 0.074      | 0.37           |
| 42  | TF-115Y-ACP9              | MicroSD holder          | 1        | LCSC        | 0.051      | 0.24           |
| 43  | IP5306                    | Battery charge IC       | 1        | LCSC        | 0.27       | 1.37           |
| 44  | TPS2116DRLR               | Power MUX IC            | 1        | LCSC        | 0.505      | 0.505          |
| 45  | TPS7A0233DBVR             | LDO                     | 1        | LCSC        | 0.453      | 0.453          |
| 46  | RT8059GJ5                 | Buck regulator          | 1        | LCSC        | 0.118      | 0.59           |
| 47  | 28K                       | Resistor                | 1        | LCSC        | 0.053      | 0.53           |
| 48  | 422K                      | Resistor                | 1        | LCSC        | 0.005      | 0.05           |
| 49  | CP2102N-A02-GQFN28R       | USB-UART converter IC   | 1        | LCSC        | 1.63       | 1.63           |
| 50  | ADS1220IPWR               | ADC IC                  | 2        | LCSC        | 2.138      | 2.138          |
| 51  | TLP250H(F)                | Optocoupler IC          | 1        | LCSC        | 1.255      | 1.255          |
| 52  | TYPE-C 16PIN              | USB-C connector         | 1        | LCSC        | 0.058      | 0.55           |
| 53  | Pressure Transducer       | Pressure transducer     | 1        | Aliexpress  | 16.26      | 17.26          |
| 54  | Inline load cell          | Load cell               | 1        | Aliexpress  | 32.5       | 33.5           |
| 55  | Straight bar load cell    | Load cell               | 2        | Aliexpress  | 2          | 3              |
| 56  | Antenna                   | Antenna                 | 3        | Aliexpress  | 2          | 3              |
|     |                           |                         |          |             | **Total**  | **88.775**     |
