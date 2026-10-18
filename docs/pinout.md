# Pinout — Isolated USB-C ESP Programmer (HC22003)

> 🏠 [HardCode — all products](https://github.com/hardcodebr) · 🛒 [Shop](https://lectronz.com/stores/hardcode-electronics) · 🌐 [hardcode.tools](https://hardcode.tools)

Isolated target header (programmer → target), **in pin order as on the board** (pin 1 → 6):

| Pin | Signal | Direction | Connect to ESP |
|-----|--------|-----------|----------------|
| 1 | **VCC** (isolated) | out (optional) | 3V3 — only if powering the target |
| 2 | **IO0 (BOOT)** | out | IO0 / boot strap |
| 3 | **EN (RST)** | out | EN / reset |
| 4 | **RX** | in  | target **TX** |
| 5 | **TX** | out | target **RX** |
| 6 | **GND** (isolated) | — | target GND |

- Logic level: **3.3 V**. Cross TX↔RX.
- The whole target side sits **behind the isolation barrier** — keep your target ground
  separate from PC/USB ground to preserve isolation.

## Pull-up jumpers (JP1 / JP2)

Next to the target header are two small **2-pin jumpers**. Each connects an optional **pull-up
(referenced to the isolated side)** onto one of the ESP's two strapping pins:

| Jumper | Pull-up on | ESP pin |
|--------|------------|---------|
| **JP1** | EN / RESET | chip-enable |
| **JP2** | IO0 / BOOT | boot strap |

- **Jumper cap fitted = pull-up ON** (referenced to the programmer's *isolated* side).
- **Ships with the caps removed (pull-ups OFF)** — the default for the isolated version.

**Why off by default.** On the isolated programmer a fitted cap ties the target's strap pin to the
programmer's isolated side. Isolation-critical, independently-powered, or mains-referenced targets
should stay referenced to their **own** supply and ground, so the caps are left off out of the box.

**Fit a cap when** you're flashing a **bare module powered from the programmer's isolated VCC** that
needs EN/IO0 held high to boot. Fit JP1 (EN), JP2 (IO0), or both as needed. Keep them **off** for any
target that has its own supply or its own pull-ups.

*(JP1/JP2 are marked on the board silkscreen. Isolation voltage rating and electrical limits:
see the product page.)*
