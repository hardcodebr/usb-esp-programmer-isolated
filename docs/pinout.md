# Pinout — Isolated USB-C ESP Programmer (HC22003)

Isolated target header (programmer → target):

| Signal | Direction | Connect to ESP |
|--------|-----------|----------------|
| **GND** (isolated) | — | target GND |
| **VCC** (isolated) | out (optional) | 3V3 — only if powering the target |
| **TX** | out | target **RX** |
| **RX** | in  | target **TX** |
| **EN (RST)** | out | EN / reset |
| **IO0 (BOOT)** | out | IO0 / boot strap |

- Logic level: **3.3 V**. Cross TX↔RX.
- The whole target side sits **behind the isolation barrier** — keep your target ground
  separate from PC/USB ground to preserve isolation.

*(Isolation voltage rating and electrical limits: see the product page.)*
