# MDBTMicro
*MDBTMicro-50Q* is an alternative board to [nRFMicro](https://github.com/joric/nrfmicro)/Pro Micro.

It has USB Type-C and optional LiPo charger, uses Raytac [MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module (or [MDBT50Q-*x*512K](https://www.raytac.com/product/ins.php?index_id=95) nRF52833 module) instead of E73-2G4M08S1.

[Open Source Hardware](https://www.oshwa.org/definition/)

> EDA: KiCad  

## PCB
|Front|Back||
|-|-|-|
|![](https://i.imgur.com/vU0cJXY.png)|![](https://i.imgur.com/LKdSV8U.png)|![](https://i.imgur.com/cjWIEYT.png)|
|![](https://i.imgur.com/ycEjVHy.jpg)|![](https://i.imgur.com/NIKhj7s.jpg)||

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

## BOM
| Ref(s)   | Value/Name         | Package/Footprint                   | Qty |
| -------- | ------------------ | ----------------------------------- | --- |
| C1, C2   | 12pF               | 0603                                | 2   |
| C3, C4   | 10uF               | 0603                                | 2   |
| D1\*     | 1N5819             | SOD-323F                            | 1   |
| J1       | USB Type-C USB 2.0 | USB Type-C Mid-Mount Receptacle 16P | 1   |
| J2       | SWD                | Pin Header 1.27mm 1x03 Vertical     | 1   |
| JP1      | Solder Jumper      | Solder Jumper                       | 1   |
| LD1\*    | Charging Indicator | 0603                                | 1   |
| LD2      | User LED           | 0603                                | 1   |
| R1\*, R5 | 1k                 | 0603                                | 2   |
| R2\*     | Rprog              | 0603                                | 1   |
| R3\*     | 820k               | 0603                                | 1   |
| R4\*     | 2M                 | 0603                                | 1   |
| R6, R7   | 5.1k               | 0603                                | 2   |
| U1\*     | XC6220B331MR-G     | SOT-25-5                            | 1   |
| U2\*     | TP4057             | SOT-23-6                            | 1   |
| U3\*     | MDBT50Q Module     | Raytac MDBT50Q                      | 1   |
| X1       | 32.768kHz          | 1610                                | 1   |

> - D1, LD1, R1, R2, and U2 is not necessary if LiPo charger is not required. 
> - R3 and R4 is not necessary if LiPo battery monitor is not required.
> - Adjust the LiPo charging current with the value of R2.
>   - 20 kΩ: 50 mA
>   - 10 kΩ: 100 mA
>   - 5 kΩ: 200 mA
>   - 4 kΩ: 250 mA
>   - 3 kΩ: 300 mA
>   - 2 kΩ: 400 mA
>   - 1.6 kΩ: 500 mA 
> - XC6220B331MR-G can be replaced by AP2112K-3.3.
> - MDBT50Q module includes MDBT50Q-1MV2/P1MV2/U1MV2 (nRF52840-based), or MDBT50Q-512K/P512K/U512K (nRF52833-based).

## Jumper
- JP1
  - nRF52840: Open
  - nRF52833: Close
