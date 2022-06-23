# GoPro Hero 11 Black

GoPro's latest camera.

[Specs](https://gopro.com/shop/cameras/hero11-black/CHDHX-111-master.html)

## HDMI

HDMI output only via the MediaMod.

The power button can be used to cycle through buttons on the camera, and the recording button can be used to select them, but this is annoying to do every time the camera is started up. This can be used to hide the camera's UI from the HDMI output.

### Clean HDMI by Default

- Install the GoPro Labs firmware. Instructions [here](https://community.gopro.com/s/article/GoPro-Labs).
- Scan this QR code:
  - ![QR code to enable clean HDMI.](../../images/gopro_labs_clean_hdmi.png)
  - Or use a QR code generator with the text: `!MHDMI=1`
  - `!MHDMI=0` restores the default operation, and `!MHDMI=2` shows any camera overlays (dirty HDMI).
- Restart the camera.
- Now when HDMI is connected the camera will automatically start in clean HDMI mode.

## Livestreaming

1080p60 over RTMP.

Instructions on how to enable livestreaming [here](https://community.gopro.com/s/article/How-To-Live-Stream-From-Your-GoPro).

To start automatic livestreaming when WiFi is connected:

- Install the GoPro Labs firmware. Instructions [here](https://community.gopro.com/s/article/GoPro-Labs).
- Follow [these instructions](https://gopro.github.io/labs/control/rtmp/) to generate the QR codes needed to configure the WiFi and RTMP.

## USB Webcam

1080p30 over USB.

Presents as a USB ethernet device when connected. Can connect to this device and using the GoPro API, start webcam streaming. This is a UDP stream to port 8554, which appears hard-coded. This means that only one webcam can easily be attached without fiddling around with differentiating the differing source addresses. Keepalives need to be sent to keep the webcam connected.

## Power Usage

HDMI: x watts.
Livestream: y watts.
USB Webcam: 4 watts.
