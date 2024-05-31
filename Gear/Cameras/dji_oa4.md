# DJI Osmo Action 4

Action camera. Obnoxious requirement to activate with an app that requires an account to be created.

[Specs](https://www.dji.com/ca/osmo-action-4/specs)

## HDMI

No HDMI output.

## Livestreaming

- Only _officially_ available through the app, untested.
- Unofficial API sort of exists, untested.

## UVC Video

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

Pixel Format: 'H264' (compressed)
Name        : H.264
        Size: Discrete 1280x720
                Interval: Discrete 0.033s (30.000 fps)
        Size: Discrete 1920x1080
                Interval: Discrete 0.033s (30.000 fps)

```

## Notes

- An app is needed to do initial set up of the camera, even if it's being used as a UVC device or recording to SD card.
- Firmware updates likely require the app to be used again.

## UVC h264 issues

- h264 output doesn't work due to buggy/missing UVC metadata, that V4l2 needs to use to determine the size of buffer to allocate to hold a frame.
- There's no `dwMaxVideoFrameBufferSize` in the H264 entry in the UVC metadata. There is an entry for MJPEG that seems to be used to calculate the buffer that is needed to be allocated.
  - There appear to be other ways to signal the potential buffer size, but none of them are used either.
- This issue appears to be a holdover from the Osmo Action 3, and therefor is probably unlikely to be fixed.
- Conceptually, one could implement a workaround for this in the kernel, specifically adding either a special case to `uvc_fixup_video_ctrl` in `drivers/media/usb/uvc/uvc_video.c` or potentially make a general fallback there.
- There doesn't seem to be a way to tell a gstreamer `v4l2src` how big of a buffer it needs, so no workarounds from that side.
- Windows seems to have some sort of fallback calculation or something, and _can_ access the device in H264 mode.

Metadata (trimmed) from v4l2-ctl:

```bash
Width/Height      : 1920/1080
Pixel Format      : 'H264' (H.264)
Bytes per Line    : 0
Size Image        : 0
```

Compare MJPEG:

```bash
Width/Height      : 1920/1080
Pixel Format      : 'MJPG' (Motion-JPEG)
Bytes per Line    : 0
Size Image        : 4147200
```

Compare working H264 device:

```bash
Width/Height      : 1920/1080
Pixel Format      : 'H264' (H.264)
Bytes per Line    : 3840
Size Image        : 4147200
```

## Power Usage

- MJPEG 1080p30: 4 watts.
- H264 1080p60: ? watts (measured on Windows).
