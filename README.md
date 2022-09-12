# MDBTMicro

MDBTMicro is an alternative to [nRFMicro](https://github.com/joric/nrfmicro)/Pro Micro board.

It's based on [Raytac MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module, with USB Type-C and LiPo charger.

[Open Source Hardware](https://www.oshwa.org/definition/)

> EDA: KiCad  

## PCB
||Front|Back|
|-|-|-|
|![](https://i.imgur.com/zdblkSl.png)|![](https://i.imgur.com/KYOEFWD.png)|![](https://i.imgur.com/FSk4QOM.png)|

## Pinout

| Pro Micro | nRF52840     | <---> | nRF52840      | Pro Micro |
| --------- | ------------ | ----- | ------------- | --------- |
| 1 (Tx)    | P0.06        |       |               | RAW       |
| 0 (Rx)    | P0.08        |       | GND           | GND       |
| GND       | GND          |       | P0.18/RESET   | RST       |
| GND       | GND          |       | VDD & VDDH    | VCC       |
| 2         | P0.15        |       | P0.30         | A3        |
| 3         | P0.17        |       | P0.31         | A2        |
| 4         | P0.20        |       | P0.29         | A1        |
| 5         | P0.13        |       | P0.02         | A0        |
| 6         | P0.24        |       | P1.13         | 15        |
| 7         | P0.09 (NFC1) |       | P0.03         | 14        |
| 8         | P0.10 (NFC2) |       | P0.28         | 16        |
| 9         | P1.06        |       | P1.11 (P1.04) | 10        |

- LED pin: P1.10
- Battery monitor pin: P0.04

> Except for the absence of `POWER_PIN`, everything else is the same as [nRFMicro 1.4](https://github.com/joric/nrfmicro/releases/tag/1.4)
