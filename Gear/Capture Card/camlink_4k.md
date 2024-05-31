# Elgato Cam Link 4k

Relatively well supported by Linux, but has a quirk where it isn't _quite_ UVC compliant, with a kernel workaround available. Probably the easiest to find HDMI capture device offering uncompressed video.

[Specs page](https://www.elgato.com/en/cam-link-4k)

## Supported Formats

### 1080p60

``` text
Pixel Format: 'YUYV'
Name        : YUYV 4:2:2
        Size: Discrete 1920x1080
                Interval: Discrete 0.017s (59.940 fps)

Pixel Format: 'NV12'
Name        : Y/CbCr 4:2:0
        Size: Discrete 1920x1080
                Interval: Discrete 0.017s (59.940 fps)

Pixel Format: 'YU12'
Name        : Planar YUV 4:2:0
        Size: Discrete 1920x1080
                Interval: Discrete 0.017s (59.940 fps)
```

### 4k30

``` text
Pixel Format: 'YUYV'
Name        : YUYV 4:2:2
        Size: Discrete 3840x2160
                Interval: Discrete 0.033s (29.970 fps)

Pixel Format: 'NV12'
Name        : Y/CbCr 4:2:0
        Size: Discrete 3840x2160
                Interval: Discrete 0.033s (29.970 fps)

Pixel Format: 'YU12'
Name        : Planar YUV 4:2:0
        Size: Discrete 3840x2160
                Interval: Discrete 0.033s (29.970 fps)
```

## Notes

- Older device firmware seemed to have the device to go sleep when it didn't have an HDMI signal. This does not appear to be the case on newer firmware versions.
- Firmware can be updated using the 4k Capture Utility available from [Elgato's downloads page](https://www.elgato.com/en/downloads).
- Needs a USB3.0 port.
- May be more stable in isochronous transfer mode over bulk.

## Power Usage

- 1080p30 NV12 capture: around 2.1 watts.
- 4k30 NV12 capture: around 3.2 watts.

## Note on colour space quirk

Background info [here](https://assortedhackery.com/patching-cam-link-to-play-nicer-on-linux/).

Basically, the camlink 4k has a firmware bug where it doesn't report the correct colour spaces, causing some apps to have weird colours when using it. It's ~~fixed~~ worked around on newer kernels, per [this Linux kernel patch](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=4c6e0976295add7f0ed94d276c04a3d6f1ea8f83).

Versions (and newer) that have the workaround:

- 4.4.276
- 4.9.276
- 4.14.240
- 4.19.198
- 5.4.134
- 5.10.52
- 5.12.19
- 5.13.4
- 5.14-rc1
