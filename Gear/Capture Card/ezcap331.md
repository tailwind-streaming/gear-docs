# ezcap331 CAM LINK 4K

Cheap uncompressed video, but quality control on the hardware is reportedly poor.

[Specs page](https://www.ezcap.com/index.php/product/ezcap331camlink4k.html)

## Supported Formats

### 4k30

Note that the BGRX (RX24) metadata appears to be garbled on some. This could be a firmware or hardware issue.

``` text
Pixel Format: 'NV12'
Name        : Y/CbCr 4:2:0
        Size: Discrete 3840x2160
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 2560x1440
                Interval: Discrete 0.017s (60.000 fps)
        Size: Discrete 1920x1080
                Interval: Discrete 0.008s (120.000 fps)
                Interval: Discrete 0.017s (60.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.017s (60.000 fps)

Pixel Format: 'YUYV'
Name        : YUYV 4:2:2
        Size: Discrete 2560x1440
                Interval: Discrete 0.020s (50.000 fps)
        Size: Discrete 1920x1080
                Interval: Discrete 0.017s (60.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.017s (60.000 fps)

Pixel Format: 'RX24'
Name        : BGRX-8-8-8-8
        Size: Discrete 1920x1080
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.017s (60.000 fps)
```

## Notes

- Needs a USB3.0 port.
- 1080p120 seems to work.
- The third entry should be XRGB8, but it doesn't appear to be read correctly on older kernels.

## Power Usage

- 1080p30 YUYV capture: 2.35 watts.
- 1080p120 NV12 capture: 3.5 watts.
- 4k30 NV12 capture: 3.65 watts.
- 1080p30 BGRX capture: 3.9 watts.
