# Capture Card Documentation

Each capture card has it's own file with notes, quirks, etc.

**Note:** The output used to generated the supported resolutions and framerates has changed. This explains the formatting differences, but the content remains unchanged.

## Notes on Power Usage Measurements

If these numbers don't match numbers elsewhere, it could be a variety of factors, including differences in test setup, hardware revisions or firmware version.

- All devices were tested, where possible, with the same test setup, using a known good USB multimeter tested against a calibrated benchtop power supply.
- All devices were fed the same video signal, for a total test duration of 10 minutes, and average power recorded.
- Devices that only do 1080p were fed a 1080p60 signal for testing.
- Devices that can accept a 2160p signal (even if scaled internally) were fed a 2160p30 signal.
- Not all devices were recorded at the same time (the first devices were tested in late 2020), so differences in test setup could affect the numbers.
  - Where possible, all devices have been re-tested with the exact same setup for power usage numbers to allow a more "apples-to-apples" comparison.
- For framerates over 60fps, devices were tested with a camera with 120fps output over HDMI. I don't have a monitor that does over 60fps over HDMI, so I was unable to verify if the signal was actually 120fps.

## List of Cards

| Card Info | Type |
| --- | --- |
| [Elgato Camlink 4k](camlink_4k.md) | HDMI -> USB3 |
| [Avermedia ExtremeCap UCV (BU110)](BU110.md) | HDMI -> USB3 |
| [Avermedia Live Streamer CAP 4K (BU113)](BU113.md) | HDMI -> USB3 |
| [Avermedia Live Gamer Mini (GC311)](gc311.md) | HDMI -> USB2 |
| [Avermedia Live Gamer Portable 2 Plus](gc513.md) | HDMI -> USB2 |
| [Avermedia Live Gamer Extreme 3](gc551g2.md) | HDMI -> USB3 |
| [Generic Macrosilicon MS2109 (the "can'tlink")](ms2109.md) |  HDMI -> USB2 |
| [Mirabox Game Capture (1080p, old version)](mirabox_1080p.md) | HDMI -> USB3 |
| [ezcap331 (CAM LINK 4K)](ezcap331.md) | HDMI -> USB3 |
| [TC358743 HDMI to CSI-2 Bridge](tc358743.md) | HDMI -> MIPI CSI-2 |
