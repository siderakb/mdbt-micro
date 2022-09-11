# MDBTMicro

A Pro Micro/[nRFMicro](https://github.com/joric/nrfmicro) compatible Bluetooth board  
with USB Type-C and LiPo charger  
using [Raytac MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module

[Open Source Hardware](https://www.oshwa.org/definition/)

## PCB
||Front|Back|
|-|-|-|
|![](https://imgur.com/070rcu8.png?1)|![](https://imgur.com/7bKrlxk.png?1)|![](https://imgur.com/uhO9zm3.png?1)|

## Pin Map

| Pro Micro | ATmega32U4 | nRF52840     | <-> | nRF52840      | ATmega32u4 | Pro Micro |
| --------- | ---------- | ------------ | --- | ------------- | ---------- | --------- |
| 1 (Tx)    | PD3        | P0.06        |     |               |            | RAW       |
| 0 (Rx)    | PD2        | P0.08        |     |               |            | GND       |
| GND       |            |              |     | P0.18/RESET   | RESET      | RST       |
| GND       |            |              |     | VDD & VDDH    |            | VCC       |
| 2         | PD1        | P0.15        |     | P0.30         | PF4        | A3        |
| 3         | PD0        | P0.17        |     | P0.31         | PF5        | A2        |
| 4         | PD4        | P0.20        |     | P0.29         | PF6        | A1        |
| 5         | PC6        | P0.13        |     | P0.02         | PF7        | A0        |
| 6         | PD7        | P0.24        |     | P1.13         | PB1        | 15        |
| 7         | PE6        | P0.09 (NFC1) |     | P0.03         | PB3        | 14        |
| 8         | PB4        | P0.10 (NFC2) |     | P0.28         | PB2        | 16        |
| 9         | PB5        | P1.06        |     | P1.11 (P1.04) | PB6        | 10        |

- LED pin: P1.10
- Battery monitor pin: P0.04

> Almost the same as [nRFMicro 1.4](https://github.com/joric/nrfmicro/releases/tag/1.4)

## EDA
- KiCAD
