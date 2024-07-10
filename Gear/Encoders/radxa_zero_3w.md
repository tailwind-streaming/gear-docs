# Radxa Zero 3W

Small, Raspberry Pi Zero 2W equivalent, with hardware HEVC encoder capable of 1080p60.

The Zero 3E version substitutes the WiFi for Ethernet (optionally supporting PoE), and is probably less useful for streaming.

The board also has a 22-pin MIPI-CSI2 port, which works well with a [TC358743](../../Gear/Capture%20Card/tc358743) based HDMI capture card, with audio capture over i2s via the 40-pin GPIO header.

## USB Ports

The board has two USB ports. The one closest to the short edge of the board is USB2, supports OTG mode and is connected to the board's power circuitry. The other USB port is USB3, and can only be used in host mode.

To toggle the USB2 port into host mode (to be able to use a hub, for example), the `rk3568-dwc3-host.dtbo` overlay need to be applied.

## Quirks/Issues

- The SD card slot is quite slow.

## Power Usage

Capturing a 1080p60 signal from a [C790](../../Gear/Capture%20Card/tc358743), encoding to 4.5Mb/s HEVC and streaming via SRT over WiFi is around 3.2 watts.
