# Insta360 One RS

GoPro like camera with different camera modules, including a normal camera, a 360 modules with two fisheye cameras and a 1" sensor size module.

[Specs](https://www.insta360.com/product/insta360-oners)

## HDMI

No HDMI output.

## Livestreaming

- Only _officially_ available through the app, untested.
- Unofficial API exists that allows livestreaming without the app, untested.

## UVC Video

Exposes a UVC device when connected over USB, so it can be used like a normal capture device.

Using the normal 360 module produces two 1920x540 images that are vertically stacked and made linear, rather than outputting any sort of 360 video.

Supported UVC formats:

``` text
Pixel Format: 'MJPG' (compressed)
Name        : Motion-JPEG
        Size: Discrete 1920x1080
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 1280x720
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 640x360
                Interval: Discrete 0.033s (30.000 fps)
```

## Notes

An unofficial API exists to access the camera via a network, but is very poor.

## Power Usage

USB normal camera: 4 watts.\
USB 360 camera: y watts.
