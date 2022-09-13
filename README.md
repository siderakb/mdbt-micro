# MDBTMicro

*MDBTMicro-50Q* is an alternative to [nRFMicro](https://github.com/joric/nrfmicro)/Pro Micro board.

It's based on Raytac [MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module, or [MDBT50Q-*x*512K](https://www.raytac.com/product/ins.php?index_id=95) nRF52833 module, with USB Type-C and optional LiPo charger.

[Open Source Hardware](https://www.oshwa.org/definition/)

> EDA: KiCad  

## PCB
||Front|Back|
|-|-|-|
|![](https://i.imgur.com/cjWIEYT.png)|![](https://i.imgur.com/vU0cJXY.png)|![](https://i.imgur.com/LKdSV8U.png)|

## Pinout

| MDBTMicro-50Q 1.0 | nRFMicro 1.4 | Pro Micro |    <-->     | Pro Micro | nRFMicro 1.4 | MDBTMicro-50Q 1.0 |
| :---------------: | :----------: | :-------: | :---------: | :-------: | :----------: | :---------------: |
|        GND        |     GND      |    --     |             |    --     |     VBAT     |       VBAT        |
|       P0.06       |    P0.06     |   D1/Tx   |             |    RAW    |     VBAT     |    VBUS (USB)     |
|       P0.08       |    P0.08     |   D0/Rx   |             |    GND    |     GND      |        GND        |
|        GND        |     GND      |    GND    |             |    RST    | P0.18/RESET  |    P0.18/RESET    |
|        GND        |     GND      |    GND    |             |    VCC    |  VDD & VDDH  |    VDD & VDDH     |
|       P0.15       |    P0.15     |    D2     |             |    A3     |    P0.30     |       P0.30       |
|       P0.17       |    P0.17     |    D3     |             |    A2     |    P0.31     |       P0.31       |
|       P0.20       |    P0.20     |    D4     |             |    A1     |    P0.29     |       P0.29       |
|       P0.13       |    P0.13     |    D5     |             |    A0     |    P0.02     |       P0.02       |
|       P0.24       |    P0.24     |    D6     |             |    D15    |    P1.13     |  P1.13 (*P1.05*)  |
|       P0.09       |    P0.09     |    D7     |             |    D14    |    P0.03     |       P0.03       |
|       P0.10       |    P0.10     |    D8     |             |    D16    |    P0.28     |       P0.28       |
|       P1.06       |    P1.06     |    D9     |             |    D10    |    P1.11     |  P1.11 (*P1.04*)  |
|                   |              |           |             |           |              |                   |
|  P1.10 (*P0.25*)  |    P1.10     |    --     |   LED Pin   |           |              |                   |
|       P0.04       |    P0.04     |    --     | Battery Pin |           |              |                   |
|         --        |    P1.09     |    --     |  Power Pin  |           |              |                   |

> Italics in brackets for nRF52833 pins, otherwise nRF52840.  
> Almost the same as [nRFMicro 1.4](https://github.com/joric/nrfmicro/releases/tag/1.4)

## Jumper
- JP1
  - nRF52840: Open (OFF)
  - nRF52833: Close (ON)
