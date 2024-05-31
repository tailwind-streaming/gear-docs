# Jetson Nano

The biggest issue with the Jetson Nano dev boards is power them.

## Power Notes

The internal USB Hub in the Jetson Nano dev board supplies a maximum of around 1.2A (check this value). This means that any power hungry devices, such as modems, capture cards or cameras will not get enough power from it and will require an external, powered hub.

On a 4GB dev-board, power is delivered at 5V through one of three ways:

- 2A via the onboard micro-USB connector.
- 4A via the barrel jack.
- 6A via 3A on each of the two 5V GPIO pins.

On a 2GB dev-board, power is delivered at 5V through one of two ways:

- 3A via the USB-c connector. This connector does not support USB-pd.
- 5A via 2.5A on each of the two 5V GPIO pins.

The Jetson Nano itself requires at least 2A (or so) to power the encoder and a connected device or two. This is out of the range of the micro-USB connector on the 4GB dev board.

Testing has also shown that many battery banks and wall-chargers claiming to deliver 2.4A can't do so, so a source that can reliably deliver at least 3A is reccomended.

## USB Notes

- The Jetson Nano dev board's USB3.0 ports are all connected to the same hub.
