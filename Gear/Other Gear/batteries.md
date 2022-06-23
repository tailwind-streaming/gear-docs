# Batteries

## Jetson Nano Notes

The internal USB Hub in the Jetson Nano dev board supplies a maximum of around 1.2A (check this value). This means that any power hungry devices, such as modems, capture cards or cameras will not get enough power from it and will require an external, powered hub.

On a 4GB dev-board, power is delivered at 5V through one of three ways:

- 2A via the onboard micro-USB connector.
- 4A via the barrel jack.
- 6A via 3A on each of the two 5V GPIO pins.

On a 2GB dev-board, power is delivered at 5V through one of two ways:

- 3A via the USB-c connector. This connector does not support USB-pd.
- 5A via 2.5A on each of the two 5V GPIO pins.

## USB Batter Packs

Finding a battery pack that can actually put out enough current at 5V can be a challenge to power the Jetson Nano.

| Model | Specs | Notes |
| --- | --- | --- |
 