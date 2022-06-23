# ezcap331 CAM LINK 4K

Cheap uncompressed video, but quality control on the hardware is reportedly poor.

[Specs page](https://www.ezcap.com/index.php/product/ezcap331camlink4k.html)

## Supported Formats

## 1080p

```
fill
```

### 4k30

```
Index       : 0
Type        : Video Capture
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

Index       : 1
Type        : Video Capture
Pixel Format: 'YUYV'
Name        : YUYV 4:2:2
        Size: Discrete 2560x1440
                Interval: Discrete 0.020s (50.000 fps)
        Size: Discrete 1920x1080
                Interval: Discrete 0.017s (60.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.017s (60.000 fps)

Index       : 2
Type        : Video Capture
Pixel Format: ''
Name        : e436eb7e-524f-11ce-9f53-0020af0
        Size: Discrete 1920x1080
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.017s (60.000 fps)
```

## Notes

- Needs a USB3.0 port.
- 1080p120 seems to work well.
- The third entry should be XRGB8, but it doesn't appear to be read correctly on older kernels.

## Power Usage

- 1080p30 YUYV capture: x watts.
- 4k30 NV12 capture: y watts.
