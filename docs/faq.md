# FAQ / Troubleshooting — HC22003 (Isolated)

> 🏠 [HardCode — all products](https://github.com/hardcodebr) · 🛒 [Shop](https://lectronz.com/stores/hardcode-electronics) · 🌐 [hardcode.com.br](https://hardcode.com.br)

**How is this different from the HC22002?**
Same flashing function, plus a galvanic isolation barrier between your PC and the target —
for mains-referenced, independently powered, or different-ground targets.

**Can I power the target from the programmer?**
Yes, over the isolated VCC line for small modules. For independently powered targets, leave
VCC disconnected and keep grounds separate.

**Flashing fails or times out.**
Check TX↔RX crossed, GND connected, target powered. Lower the baud rate and retry.

**Do I lose isolation if I connect both supplies?**
Yes — don't bridge the target ground to PC/USB ground.

**What are the two little jumpers (JP1 / JP2) for?**
They enable a pull-up (referenced to the isolated side) on **EN** (JP1) and **IO0** (JP2). They ship
**removed** so your target stays referenced to its own supply/ground. Fit a cap only when flashing a
bare module powered from the programmer's isolated VCC. See
[Pinout → Pull-up jumpers](pinout.md#pull-up-jumpers-jp1--jp2).

More help: support@hardcode.com.br
