# Parts and budget draft

Checked 16 November 2026 for UK delivery. Candidate parts only. Not a completed funding BOM; no order placed.

| Ref | Candidate / supplier | Buy qty | Unit GBP | Total GBP | Check |
|---|---|---:|---:|---:|---|
| U1 | [XIAO ESP32C3 (loose headers)](https://thepihut.com/products/seeed-xiao-esp32c3) — The Pi Hut | 1 | 5.40 | 5.40 | Select loose headers for current SMD footprint; confirm underside pads. |
| J1 | [HCMODU0164 SSD1306 OLED](https://hobbycomponents.com/displays/1160-096-i2c-iic-oled-module) — Hobby Components | 1 | 3.33 | 3.33 | Price EXCLUDES VAT. 3.3V, GND/VCC/SCL/SDA; confirm hole positions. |
| J2 | [ST071 GY-521 MPU6050](https://www.bitsboxuk.com/index.php?main_page=product_info&products_id=3059) — Bitsbox | 1 | 3.27 | 3.27 | STARTING price; confirm chosen variant, dimensions and pin order. |
| U2 | [ST092 bare four-pin DHT11](https://www.bitsboxuk.com/index.php?main_page=product_info&products_id=3679) — Bitsbox | 1 | 1.85 | 1.85 | Seller specifies 3-5V and VCC/DATA/NC/GND. Not a three-pin breakout. |
| SW1/SW2 | [CHERRY MX1A-G1NW PCB-mount brown](https://www.keyboardco.com/product/cherry-key-switch-module-brown-tactile-pcb-mount.asp) — Keyboard Company | 2 | 0.48 | 0.96 | Five-hole PCB-mount version; keycaps not included. |
| R1 | [MR2510K 10k axial resistor](https://www.bitsboxuk.com/index.php?cPath=83_88&main_page=product_info&products_id=594) — Bitsbox | 10 | 0.06 | 0.60 | Minimum purchase 10; fit one at 7.62mm lead spacing. |
| Headers | [CN344 40-way 2.54mm strip](https://www.bitsboxuk.com/index.php?cPath=225_230&main_page=product_info&products_id=2409) — Bitsbox | 1 | 0.24 | 0.24 | Cut to module lengths; check included module headers first. |

Listed-price subtotal: **GBP 15.65**, excluding OLED VAT and any MPU6050 variant premium. Other component prices include VAT according to the cited seller pages.

## Delivery and PCB quote

- [Pi Hut UK delivery](https://thepihut.com/pages/delivery): Royal Mail 1st Class GBP 3.80; confirm at checkout.
- [Bitsbox UK delivery](https://bitsboxuk.com/?main_page=shippinginfo): Royal Mail 48 GBP 2.50; confirm at checkout.
- [Hobby Components delivery](https://hobbycomponents.com/content/1-delivery): price requires checkout quote.
- Keyboard Company delivery: not yet quoted.
- [JLCPCB advertises a USD 2 base option for five two-layer boards up to 100 x 100mm](https://jlcpcb.com/help/article/how-do-i-place-an-order). Our outline is 70 x 75mm. This is NOT a quotation for this order.
- [PCB shipping depends on weight, destination and service](https://jlcpcb.com/help/article/how-much-does-shipping-cost). PCB tax and shipping are not yet quoted.

## Budget result

[Wise historical rate for 16 November 2026](https://wise.com/us/currency-converter/gbp-to-usd-rate/history/16-11-2026) showed approximately GBP 1 = USD 1.322. Planning conversion only; card rate/fees may differ.

Parts GBP 15.65 + two known shipping charges GBP 6.30 = GBP 21.95. At the planning rate this is USD 29.02; adding only the advertised USD 2 PCB base option gives **USD 31.02**.

This already exceeds the dashboard's **USD 30 Tier 1 budget**, BEFORE OLED VAT, two other suppliers' postage, PCB postage/tax, any variant premium, a USB data cable if needed, or exchange fees. This supplier combination is not ready to submit as a USD 30 order.

## Finish before submitting

1. Consolidate suppliers or obtain verified cheaper compatible listings. Headline promotional prices are not final checkout totals.
2. Obtain an actual PCB quote and complete hardware fit checks. Do not order yet.
3. Check the programme's supported PCB ordering route or actual eligibility for another funding tier. No higher tier is assumed approved.
4. Enter actual purchase quantities, vendor URLs, USD prices, tax and shipping once each in the dashboard. Keep tools separate as the dashboard instructs.

## Hardware review

DRC passes do not verify purchased parts. Confirm XIAO underside pads and soldering method, OLED hole positions and power pin order, MPU6050 variant dimensions/orientation, DHT11 pin pitch/orientation, and USB/module clearances. See [Seeed hardware resources](https://wiki.seeedstudio.com/XIAO_ESP32C3_Getting_Started/#resources).

The current circuit uses SDA on D5/GPIO7 and SCL on D4/GPIO6. These must be explicitly mapped in eventual firmware. The source guide has a contradictory example swapping these two constants. No firmware is included or claimed tested.

An existing USB-C data cable may be reused. Optional keycaps and tools are not included in these totals.
