# FAQ / Troubleshooting — HC22003 (Isolated)

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

More help: support@hardcode.com.br
