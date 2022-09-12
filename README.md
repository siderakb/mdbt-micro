# MDBTMicro

*MDBTMicro-50Q* is an alternative to [nRFMicro](https://github.com/joric/nrfmicro)/Pro Micro board.

It's based on Raytac [MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module, or [MDBT50Q-*x*512K](https://www.raytac.com/product/ins.php?index_id=95) nRF52833 module, with USB Type-C and LiPo charger.

[Open Source Hardware](https://www.oshwa.org/definition/)

> EDA: KiCad  

## PCB
||Front|Back|
|-|-|-|
|![](https://i.imgur.com/zdblkSl.png)|![](https://i.imgur.com/KYOEFWD.png)|![](https://i.imgur.com/FSk4QOM.png)|

## Pinout

| Pro Micro | nRF52840     | nRF52833     | <---> | nRF52833    | nRF52840    | Pro Micro |
| --------- | ------------ | ------------ | ----- | ----------- | ----------- | --------- |
| D1 (Tx)   | P0.06        | P0.06        |       |             |             | RAW       |
| D0 (Rx)   | P0.08        | P0.08        |       | GND         | GND         | GND       |
| GND       | GND          | GND          |       | P0.18/RESET | P0.18/RESET | RST       |
| GND       | GND          | GND          |       | VDD & VDDH  | VDD & VDDH  | VCC       |
| D2        | P0.15        | P0.15        |       | P0.30       | P0.30       | A3        |
| D3        | P0.17        | P0.17        |       | P0.31       | P0.31       | A2        |
| D4        | P0.20        | P0.20        |       | P0.29       | P0.29       | A1        |
| D5        | P0.13        | P0.13        |       | P0.02       | P0.02       | A0        |
| D6        | P0.24        | P0.24        |       | ***P1.05*** | ***P1.13*** | D15       |
| D7        | P0.09 (NFC1) | P0.09 (NFC1) |       | P0.03       | P0.03       | D14       |
| D8        | P0.10 (NFC2) | P0.10 (NFC2) |       | P0.28       | P0.28       | D16       |
| D9        | P1.06        | P1.06        |       | ***P1.04*** | ***P1.11*** | D10       |

- LED pin: P1.10 (nRF52840) or P0.25 (nRF52833)
- Battery monitor pin: P0.04

> Except for the absence of `POWER_PIN`, everything else is the same as [nRFMicro 1.4](https://github.com/joric/nrfmicro/releases/tag/1.4)

## Jumper
- JP1
  - nRF52840: Open (OFF)
  - nRF52833: Close (ON)
