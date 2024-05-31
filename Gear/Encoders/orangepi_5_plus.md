# Orange Pi 5 Plus

RK3588 based SBC with onboard HDMI Input

## USB Notes

Board has 2x USB2.0 USB-A ports, 2x USB3.0 USB-A ports and 1 USB3.0 USB-C port (there's also a USB-C port for power only).

| Port Location | USB2.0 Bus | USB3.0 Bus |
| --- | --- | --- |
| Back top white | 2 | - |
| Back bottom white | 1 | - |
| Front top blue | 5 | 6 |
| Front bottom blue | 5 | 6 |
| Front USB-c | 5 | 6 |

### HDMI RX

Maximum resolution: 4096x2160

Supported video formats:

- BGR3: RGB 8-8-8
- NV24: Y/CbCr 4:4:4
- NV16: Y/CbCr 4:2:2
- NV13: Y/CbCr 4:2:0

### Disabling CPU Cores

CPU cores can be disabled in an attempt to save power, but in order for HDMI RX to work correctly, the first A76 core (#4) needs to be enabled. Two A55 cores, however, can be used for USB based encoders. Power saving, however, were minimal (100-200mW best case, potentially lower) and probably not worth it.

### Power Usage

Approximately 3.8W to capture a 1080p60 (BGRe format) input on HDMI in, encode and transmit over WiFi (Intel AX210 card). Different settings and peripherals, such as NVMe drives, wireless cards, etc can change power usage, so use this as a _guideline_.
