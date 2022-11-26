# Changelog

## [1.4.0]
### Removed
- Remove USB D+/- test pads.

### Changed
- Change SWD connecter footprint, makes it easier to solder.

## [1.3.0] 2022-Oct-18
### Added
- USB D+/- test pads added.

### Changed
- Replace all capacitors, resistors and LEDs footprint back to 0603 again, except R5 and LD3.

## [1.2.0] 2022-Oct-16
### Fixed
- Fixed the ProMicro board 2.54mm pin headers hole size from 0.7mm to 1mm.

### Added
- LD3 VBUS power indicator.

### Changed
- Move C1 and C2 away from the back of USB D+/- differential pair tracks.
- Reduce the size of board to 33.02x17.78mm (1.3x0.7 inch, same as ProMicro).

## [1.1.0] 2022-Oct-15
### Added
- Q1 P-MOSFET for LiPo battery load sharing.
- Q2 P-MOSFET for output Vcc switch.

### Changed
- Replace all capacitors, resistors and LEDs footprint from 0603 to 0402.
- Replace X1 crystal footprint from 1610 to 3215.
- Replace SWD connector from 1.27mm pin header to test pad (TP8 ~ TP10).
- Update the USB Type-C footprint.

## [1.0.0] 2022-Sep-13
First release.
