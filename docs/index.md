# Quick-Start — Isolated USB-C ESP Programmer (HC22003)

The flashing workflow is identical to the non-isolated programmer — the isolation is
transparent to your tools.

## 1. Connect
- Plug into your PC with the included **USB-C** cable.
- Wire the **isolated** target header to your ESP (see **[Pinout](pinout.md)**):
  `TX→RX, RX→TX, EN, IO0, GND`, and isolated `VCC` if powering the target.
- Install the USB-to-serial driver for your OS if it isn't detected automatically.

## 2. Select
- In **esptool / Arduino IDE / ESP-IDF**, choose your board and the programmer's serial port.

## 3. Flash
- Upload. **Auto-reset** enters download mode and resets the target automatically.

## Notes on isolation
- The target side is galvanically isolated from your PC/USB ground.
- Power the target either from the programmer's **isolated** VCC, or from its own supply —
  do not bridge the two grounds, or you defeat the isolation.

Trouble? See the **[FAQ](faq.md)**.

## 💬 Feedback & suggestions
Ideas, questions, or something you'd like to see? Open a discussion — we read every one:
**https://github.com/hardcodebr/usb-esp-programmer-isolated/discussions**

## 🛠️ Custom designs
Need a custom board or a tweak to this one? We do custom design work — **support@hardcode.com.br**
