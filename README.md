# Starbie — routed PCB for review

Starbie is a beginner electronics project based on the [Starbie Week 1 guide](https://github.com/SharKingStudios/Starbie/blob/main/Week%201%20Guide.md). It combines a Seeed XIAO ESP32-C3, two buttons, an OLED display connection, a motion-sensor connection and a DHT11 temperature/humidity sensor.

## Current status — 16 November 2026

- Full schematic and seven physical component footprints included.
- 70 × 75 mm rounded board with USB access at its top edge.
- All 20 previously outstanding connections routed on two copper layers.
- 0.30 mm tracks; 10 through vias, 0.60 mm diameter / 0.30 mm drill.
- KiCad 10 DRC: **0 violations, 0 unconnected items, 0 schematic parity issues**. The JSON report is in `checks/`.
- Gerber and plated/non-plated drill files exported into `manufacturing_review/`.
- No hardware has been assembled, powered or tested. Firmware is not implemented in this package.

This is a routed review version, not an authorization to order. Exact purchased module dimensions, pin order and assembly method still need checking. A clean DRC confirms consistency with the digital design rules; it does not prove that a selected module fits or that the physical device works. The routing includes vias near/within controller pads, which should be reviewed for the intended soldering method before manufacture.

## Opening the project

Extract the entire folder and open `Starbie.kicad_pro` in KiCad 10. Keep the `Week 1 Care Package` folder beside the project files: the symbol and footprint libraries use project-relative paths. Open the PCB Editor to see the new copper routing. The earlier placement-only project remains a separate copy.

![Routed PCB](images/Starbie_Routed_PCB.png)

Red tracks are front copper; blue tracks are back copper. Vias are plated holes connecting the two sides. No ground pour has been added; ground is connected using tracks.

## Connections for eventual firmware

| Function | XIAO label | ESP32-C3 GPIO |
|---|---|---|
| OLED / MPU6050 SDA | D5 | GPIO7 |
| OLED / MPU6050 SCL | D4 | GPIO6 |
| DHT11 DATA | D1 | GPIO3 |
| Button SW1 | D2 | GPIO4 |
| Button SW2 | D3 | GPIO5 |

The I²C assignment is deliberately explicit: eventual firmware should initialize SDA on GPIO7 and SCL on GPIO6. Both buttons connect to GND when pressed and require the corresponding input pull-ups in firmware. MPU6050 AD0 is tied to GND; check address 0x68 when testing. R1 is a 10 kΩ pull-up from DHT_DATA to 3V3. Power is intended through the XIAO's USB connector; VBAT and VBUS pads are not connected on this carrier board.

## Parts to source and price

| Reference | Part | Quantity / purchase note |
|---|---|---|
| PCB | Custom 2-layer 70 × 75 mm PCB | Manufacturer's minimum quantity; include shipping and tax |
| U1 | Seeed Studio XIAO ESP32-C3 | 1, matching bundled SMD footprint |
| SW1, SW2 | Cherry MX-compatible PCB-mount pushbuttons | 2, matching the 5-pin footprint |
| J1 | SSD1306 I²C OLED module | 1, pin order GND / VDD / SCL / SDA; verify mounting dimensions |
| J2 | GY-521 / MPU6050 module | 1, matching 8-pin connector footprint |
| U2 | Bare 4-pin DHT11 | 1; verify supply specification and pinout of the selected part |
| R1 | 10 kΩ axial resistor | 1, 7.62 mm lead spacing |
| Connectors | Module headers / sockets | As required for chosen mounting approach |

Candidate parts, vendor links and listed prices are in [SOURCING.md](SOURCING.md). The initial UK supplier combination exceeds the dashboard's $30 budget before all delivery charges and tax. The funding BOM and hardware compatibility checks remain unfinished. Tools are handled separately by the programme's shop.

## Remaining work

1. Select exact compatible parts and confirm their documentation, dimensions and connector order.
2. Review soldering access, module clearances, USB access and any enclosure needs.
3. Recheck/export if any footprint or placement changes are needed.
4. Prepare a real priced BOM within the approved budget and publish the project repository.
5. Document the participant's active learning/work ; submit through the programme's checklist.
6. After approval, assemble and test the hardware, then implement and test firmware.

## Attribution

This project follows SharKingStudios' Starbie tutorial. Schematic completion/checks, footprint corrections, component placement, automated PCB routing, validation, exports and documentation. The participant should review and understand these changes and report their own active work accurately. No claimed working hours are supplied by this package.
