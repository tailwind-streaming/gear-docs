# Mirabox Game Capture Card, 1080p (Yellow and Black)

Cheap uncompressed and compressed video. New versions seemingly using inferior chip. Avoid.

[Specs page](https://miraboxbuy.com/collections/capture-card/products/mirabox-game-capture-card-usb3-1-type-c-hdmi-capture-card-1080p-60fps-hd-audio-video-capture-device-camlink-for-ps4-switch-obs-youtube-live-streaming-and-recording-compatible-with-windows-mac-os-linux)

## Supported Formats

### 1080p

```bash
Index       : 0
Type        : Video Capture
Pixel Format: 'MJPG' (compressed)
Name        : Motion-JPEG
Size: Discrete 1920x1080
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 640x480
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 800x600
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1024x768
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x720
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x960
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x1024
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1360x768
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1400x900
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1440x900
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)

Index       : 1
Type        : Video Capture
Pixel Format: 'YUYV'
Name        : YUYV 4:2:2
Size: Discrete 1920x1080
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 640x480
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 800x600
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1024x768
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x720
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x960
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1280x1024
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1360x768
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1400x900
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)
Size: Discrete 1440x900
        Interval: Discrete 0.017s (60.000 fps)
        Interval: Discrete 0.033s (30.000 fps)

```

## Notes

- Current versions are apparently shipping with an inferior [MacroSilicon MS2109](ms2109.md) chip.
- Needs a USB3.0 port for YUYV capture.
- Actual chip made by "SunPlus Innovation Technology"
- USB-c port appears to only work in one orientation.
- Can be picky about kernels, and it doesn't seem quite fully UVC compatible.

## Power Usage

- 1080p30 YUYV capture: x watts.
- 1080p30 MJPEG capture: x watts.
