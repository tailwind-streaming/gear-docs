# USB Bandwidth Notes

## General Notes

USB3.0 has been superceded by USB3.1, which has been superceded by USB3.2 Gen 1. USB3.0 (or just USB3) is used for clarity's sake throughout this documentation.

## USB Reservation

### Jetson Nano Dev Board Example

Using the Jetson Nano devboard as an example, all the USB3 ports are connected to a hub with the same USB root ports.

This means that in normal usage, only one raw capture (USB3) device can be connected at once. This is to do with exhausting total USB bandwidth. Even if the mode the device is using is less, the maximum possible bandwidth is reserved in most cases. So if a raw capture device supports 2160p, but is only being used for 1080p, another raw capture device will not be able to be used, even if there's leftover bandwidth for the lower resolution. This also goes for _some_ devices that support raw capture and compressed capture.

There are some workaround for this, but unfortunately, this means that only one raw (uncompressed, to not MJPEG or H264) USB capture device can be used at a time.

Bandwidth is not shared between USB2.0 and USB3.0 devices, but for raw devices, this doesn't make much difference as USB2.0 doesn't have enough bandwidth for reasonable resolutions/framerates.

Note: This limitation does not apply to CSI-2 capture devices, which don't use USB.

## Ingest Considerations

Many board have only one USB3 root exposed, so only one raw USB capture device will be supported at a time. This also applies to USB2 devices, though there's likely at least two USB2 roots, one used on the USB3 ports and one used on the USB2 ports.

## Some Selected Bandwidths Needed

Caveats:

- Compressed bandwidths (MJPEG, H264, H265) vary by bitrate, so the below values are guides based on what the UVC drivers are reporting for test devices.
- Some capture devices report a high bandwidth need than they use, even for their highest bandwidth capture mode.
- See (Chrome Subsampling Notes)[]

| Resolution | Format | Framerate (fps) | Bandwidth Estimate | Notes |
| --- | --- | --- | --- | --- |
| 1080p | NV12 | 25 | 600Mb/s | 25fps more common in Europe than North America. |
| 1080p | NV16 | 25 | 800Mb/s | 25fps more common in Europe than North America. |
| 1080p | NV24 | 25 | 1.2Gb/s | 25fps more common in Europe than North America. |
| 1080p | NV12 | 30 | 750Mb/s | 12 bits/pixel |
| 1080p | NV16 | 30 | 1Gb/s | 16 bits/pixel |
| 1080p | NV24| 30 | 1.5Gb/s | 24 bits/pixel |
| 1080p | NV12 | 50 | 1.24Gb/s | 50 fps more common in Europe than North America. |
| 1080p | NV16 | 50 | 1.65Gb/s | 50 fps more common in Europe than North America. |
| 1080p | NV12 | 60 | 1.5Gb/s | 12 bits/pixel |
| 1080p | NV16| 60 | 2Gb/s | 16 bits/pixel |
| 1080p | NV24 | 60 | 3Gb/s | 24 bits/pixel |
| 1080p | RGBX | 60 | 4Gb/s | 8+8+8+8=32 bits/pixel |
| 1080p | MJPEG | 30 | 60Mb/s | Measured USB usage on an MJPEG device |
| 1080p | H264 | 60 | 16Mb/s | Measured USB usage on an H264 device |
| 1080p | P010 | 30 | 933Mb/s | P010 is 4:2:0 10-bit,30/2=15 bits/pixel |
| 1080p | P010 | 60 | 1.87Gb/s | P010 is 4:2:0 10-bit, 30/2=15 bits/pixel |
| 1080p | NV12 | 120 | 3Gb/s |  |
| 1440p | NV12 | 60 | 2.65Gb/s |  |
| 2160p | NV12 | 30 | 3Gb/s |  |
| 2160p | NV12 | 60 | 6Gb/s | Exceeds USB3. |
| 2160p | NV16 | 30 | 4Gb/s |  |
| 2160p | NV16 | 60 | 8Gb/s | Exceeds USB3. |
| 2160p | NV24 | 30 | 6Gb/s | Exceeds USB3. |
| C4k | NV16 | 24 | 3.4Gb/s | 4096x2160 |

- USB2.0: 480Mb/s maximum.
- USB3.0: 5Gb/s maximum.
- USB3.2 Gen 2x1: 10Gb/s maximum.
- USB3.2 Gen 2x2: 20Gb/s maximum.
