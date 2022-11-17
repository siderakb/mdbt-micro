# MDBTMicro

![](https://i.imgur.com/TniY3Ef.jpg)

*MDBTMicro-50Q* is an alternative board to [nRFMicro](https://github.com/joric/nrfmicro)/Pro Micro.

It has USB Type-C and optional LiPo charger, uses Raytac [MDBT50Q-*x*1MV2](https://www.raytac.com/product/ins.php?index_id=24) nRF52840 module (or [MDBT50Q-*x*512K](https://www.raytac.com/product/ins.php?index_id=95) nRF52833 module) instead of E73-2G4M08S1.

Go to [Releases](https://github.com/ziteh/mdbt-micro/releases) for schematic and Gerber files.

> A part of [ErgoSNM keyboard](https://github.com/ziteh/ergo-snm-keyboard).  
> EDA: KiCad  

## PCB
| Front                                | Back                                 | Layers                               |
| ------------------------------------ | ------------------------------------ | ------------------------------------ |
| ![](https://i.imgur.com/6SuUTsl.jpg) | ![](https://i.imgur.com/FZB4fCI.jpg) | ![](https://i.imgur.com/3PWzDsE.jpg) |
| ![](https://i.imgur.com/D5TRWvf.jpg) | ![](https://i.imgur.com/wxiYFGp.jpg) |  |

## BOM
| Ref(s)   | Value/Name             | Package/Footprint                   | Qty |
| -------- | ---------------------- | ----------------------------------- | --- |
| C1, C2   | 1uF                    | SMD 0603 (1608 Metric)              | 2   |
| C3, C4   | 12pF                   | SMD 0603 (1608 Metric)              | 2   |
| R1       | 100k                   | SMD 0603 (1608 Metric)              | 1   |
| R2\*, R4 | 1k                     | SMD 0603 (1608 Metric)              | 2   |
| R5       | 1k                     | **SMD 0402 (1005 Metric)**\*        | 1   |
| R3\*     | *Rprog*                | SMD 0603 (1608 Metric)              | 1   |
| R6\*     | 820k                   | SMD 0603 (1608 Metric)              | 1   |
| R7\*, R8 | 2M                     | SMD 0603 (1608 Metric)              | 2   |
| R9, R10  | 5.1k                   | SMD 0603 (1608 Metric)              | 2   |
| LD1\*    | Red (Charge indicator) | SMD 0603 (1608 Metric)              | 1   |
| LD2      | Blue (User LED)        | SMD 0603 (1608 Metric)              | 1   |
| LD3      | Green (VBUS indicator) | **SMD 0402 (1005 Metric)**\*        | 1   |
| D1       | 1N5819                 | SOD-323F                            | 1   |
| J2       | USB 2.0 Type-C         | USB Type-C Mid-Mount Receptacle 16P | 1   |
| JP1      | Solder Jumper          | 1.0x1.5mm                           | 1   |
| Q1, Q2   | AO3407                 | SOT-23                              | 2   |
| U1       | XC6220B331MR-G         | SOT-23-5                            | 1   |
| U2\*     | MDBT50Q Module         | Raytac MDBT50Q                      | 1   |
| U3\*     | TP4057                 | SOT-23-6                            | 1   |
| X1       | 32.768kHz              | 3.2x1.5mm                           | 1   |

> - Please note that the footprint of R5 and LD3 is 0402.
> - R2, R3, U3 and LD1 are not necessary if LiPo charger is not required. 
> - R6 and R7 are not necessary if LiPo battery monitor is not required.
> - Adjust the LiPo charging current with the value of R3.
>   - 20 kΩ: 50 mA
>   - 10 kΩ: 100 mA
>   - 5 kΩ: 200 mA
>   - 4 kΩ: 250 mA
>   - 3 kΩ: 300 mA
>   - 2 kΩ: 400 mA
>   - 1.6 kΩ: 500 mA 
> - XC6220B331MR-G can be replaced by AP2112K-3.3.
> - MDBT50Q module includes MDBT50Q-1MV2/P1MV2/U1MV2 (nRF52840-based), or MDBT50Q-512K/P512K/U512K (nRF52833-based).

## Pinout
| MDBTMicro-50Q `1.3` | nRFMicro `1.4` | Pro Micro |    <-->     | Pro Micro | nRFMicro `1.4` | MDBTMicro-50Q `1.3` |
| :-----------------: | :------------: | :-------: | :---------: | :-------: | :------------: | :-----------------: |
|         GND         |      GND       |    --     |             |    --     |      VBAT      |        VBAT         |
|        P0.06        |     P0.06      |   D1/Tx   |             |    RAW    |      VBAT      |     VBUS (USB)      |
|        P0.08        |     P0.08      |   D0/Rx   |             |    GND    |      GND       |         GND         |
|         GND         |      GND       |    GND    |             |    RST    |  P0.18/RESET   |     P0.18/RESET     |
|         GND         |      GND       |    GND    |             |    VCC    |   VDD & VDDH   |     VDD & VDDH      |
|        P0.15        |     P0.15      |    D2     |             |    A3     |     P0.30      |        P0.30        |
|        P0.17        |     P0.17      |    D3     |             |    A2     |     P0.31      |        P0.31        |
|        P0.20        |     P0.20      |    D4     |             |    A1     |     P0.29      |        P0.29        |
|        P0.13        |     P0.13      |    D5     |             |    A0     |     P0.02      |        P0.02        |
|        P0.24        |     P0.24      |    D6     |             |    D15    |     P1.13      |   P1.13 (*P1.05*)   |
|        P0.09        |     P0.09      |    D7     |             |    D14    |     P0.03      |        P0.03        |
|        P0.10        |     P0.10      |    D8     |             |    D16    |     P0.28      |        P0.28        |
|        P1.06        |     P1.06      |    D9     |             |    D10    |     P1.11      |   P1.11 (*P1.04*)   |
|                     |                |           |             |           |                |                     |
|   P1.10 (*P0.25*)   |     P1.10      |    --     |   LED Pin   |           |                |                     |
|        P0.04        |     P0.04      |    --     | Battery Pin |           |                |                     |
|        P1.09        |     P1.09      |    --     |  Power Pin  |           |                |                     |
|   P1.12 (*P0.23*)   |       --       |    --     |     TP1     |           |                |                     |
|   P1.14 (*P1.03*)   |       --       |    --     |     TP2     |           |                |                     |
|   P1.15 (*P0.19*)   |       --       |    --     |     TP3     |           |                |                     |
|        P0.05        |       --       |    --     |     TP4     |           |                |                     |
|        P0.07        |       --       |    --     |     TP5     |           |                |                     |
|        P0.11        |       --       |    --     |     TP6     |           |                |                     |
|        P0.12        |       --       |    --     |     TP7     |           |                |                     |
|         GND         |       --       |    --     |     TP8     |           |                |                     |
|        SWDIO        |       --       |    --     |     TP9     |           |                |                     |
|        SWCLK        |       --       |    --     |    TP10     |           |                |                     |

> Italics in brackets for MDBT50Q-*x*512K (nRF52833) pins, otherwise MDBT50Q-*x*1MV2 (nRF52840).  
> Almost the same as [nRFMicro 1.4](https://github.com/joric/nrfmicro/releases/tag/1.4)

## Jumper Config
- JP1
  - nRF52840: Open
  - nRF52833: Close

## Board Characteristics
- Copper layer count: 2
- Board overall dimensions: 33.02 mm x 17.78 mm
- Min track/spacing: 0.127 mm / 0.127 mm
- Min hole diameter: 0.3 mm

## Disclaimer

See [LICENSE](./LICENSE).
