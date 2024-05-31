# Jetson Orin NX

The "cheapest" Jetson Orin board with hardware encoders. Supports hardware AV1 encoding, and is therefor very intersting.

## Encoder Notes

H265 and AV1 hardware encoders both support 10-bit encoding up to at least 4k30, so HDR might be supported.

AV1 encoder does not generate Sequence Headers on IDR frames, and therefor seems unsuitable for livestreaming. This is due to 

## Power Notes

The dev board is _much_ easier to power than a Jetson Nano, taking 5V-20V DC in via a barrel jack. This also allows it to be powered from a USB-PD trigger at various voltages, or via a 12V (or 19V laptop targeting) battery pack/car charger.

## USB Notes

- All ports connected to an internal USB3.2 Gen 2 hub capable of 10Gb/s. This should allow at least two USB3.0 raw capture devices to be used at once.
