# HaleHound-CYD — ESP32-2432S024R / ESP32-2432W328R

**Firmware:** HaleHound-CYD v3.3.0 S024R Edition  
**Forked from:** [Wontfallo/CYD-ESP32](https://github.com/anomalyco/opencode)  
**Board:** CYD ESP32-2432S024R / ESP32-2432W328R (2.4" ILI9341 + XPT2046 resistive touch)

## Key Changes from Stock CYD-2432S028R

| Feature        | S028R (2.8") | S024R (2.4")                         |
|----------------|--------------|---------------------------------------|
| Backlight      | GPIO 21      | GPIO 27                               |
| Touch SPI      | Separate VSPI (25/32/39) | Shared HSPI with TFT (12/13/14) |
| Touch CS       | GPIO 33      | GPIO 33                               |
| Touch IRQ      | GPIO 36      | GPIO 36                               |
| CC1101 CS      | GPIO 27      | GPIO 26 (27 is backlight)             |
| CC1101 TX_EN   | GPIO 26      | GPIO 25                               |

## Pin Mapping

- **TFT:** CS=15, DC=2, RST=-1, BL=27, MOSI=13, MISO=12, SCLK=14
- **Touch:** CS=33, IRQ=36, shared HSPI (MOSI=13, MISO=12, SCLK=14)
- **SD Card:** CS=5, VSPI (MOSI=23, MISO=19, SCLK=18)
- **RGB LED:** R=4, G=16, B=17
- **Radios:** CC1101 + NRF24 on VSPI bus

## Build

```bash
platformio run -e esp32-cyd-s024r
```

Flash `merged-s024r.bin` at address `0x0` using ESPTerminator or esptool.
