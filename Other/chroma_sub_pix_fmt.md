# Chroma Subsampling and Pixel Format

Ever wondered what NV16 means, and how it's different from YUYV? What's 4:4:4, 4:2:2 and 4:2:0 mean? These come up sometimes in discussions of streaming. Mostly using 4:2:0 is "good enough", especially with video that's going to be compressed, but it's good to understand the tradeoffs that are being made.

## Chroma Subsampling

For a full explanation of what this is. Wikipedia has a good [explanation](https://en.wikipedia.org/wiki/Chroma_subsampling) for how this works.

At a high-level, many video signals are split into luminance (how bright something is) and 2 chrominance channels (the colour of something, oversimplified, one channel is the blue/yellowness of the image, the other is the green/redness of an image).

Chroma subsampling exploits the fact that human eyes are much better at detecting how bright something in than what colour it is to save bandwidth/storage. A 4:4:4 image means that each group of four pixels has 4 samples for each of luminance (Y') and the 2 chrominance channels (Cb and Cr). This is equivalent to a converted RGB image at the same bit-depth. This yields 8+8+8=24 points.

A 4:2:2 subsample means 8 samples in Y', and 2 vertically and 2 horizontally Cb/Cr samples in a group of 8 pixels. This yields 8+4+4=16 points, so uses 2/3 of the bandwidth versus an image with no subsampling.

A 4:2:0 subsample means 8 samples in Y' and 2 vertically and 1 horizontal Cb/Cr samples in a group of 8 pixels. This yields 8+4+0=12 points, so 1/2 the bandwidth versus no subsampling.

Consider the following 8-pixels (2 rows and 4 columns) block of colour data:

```text
---------
|A|B|C|D|
---------
|E|F|G|H|
---------
```

For a given subsampling, we expect the pixel reults to be:

- 4:4:4 -> A, B, C, D, E, F, G, H (8 distinct values, full colour resolution)
- 4:2:2 -> AB, CD, EF, GH (4 distinct values, two number pairs are combined, half horizontal and  full vertical colour resolution)
- 4:2:0 -> ABEF. CDFH (2 distinct values, four number pairs are combined, half vertical and half horizontal colour resolution)

How the pairs are combined depends on the specific standard. In some cases, the values are averaged. In others, the first or last value is taken, and the other pixel's value(s) are ignored.

## Okay, What Does This _Mean_ for Me?

It means that raw video can use less bandwidth on the USB or memory bus and still look more-or-less as good.

| Pixel Format | Chroma Subsampling | bits/pixel (bit-depth) | Data size | Notes |
| --- | --- | --- | --- | --- |
| NV12 | 4:2:0 | 12 (8) | 1/2 | Planar YUV |
| NV16 | 4:2:2 | 16 (8) | 2/3 | Planar YUV |
| YUYV | 4:2:2 | 16 (8) | 2/3 | Packed YUV |
| NV24 | 4:4:4 | 24 (8) | 1 | Planar YUV |
| RGB8 | 4:4:4 equivalent | 24 (8) | 1 | RGB 8-8-8 |

Note: RGB doesn't have luminance or chrominance information. It just represents a colour, with brightness and what colour it is baked in.

## Compressed Formats

Not strictly a pixel format, but formats can also contain compressed video. Tthe precise way they encode colour information is determined by the codec. They tend to lose much more colour information than the rest of the pixel formats here, which greatly decreses their storage/bandwidth requirements at the expense of lower (sometime imperceptibly) quality.

Examples are: MJPEG, H264, H265, AV1...

## Planar YUV? Packed YUV?

**Note:** None of the rest really affects livestreaming much and is included for those who are curious.

Lots of this section summarized from the Linux Kernel [documentation](https://docs.kernel.org/6.8/userspace-api/media/v4l/pixfmt.html) on V4L's pixel formats.

RGB is easy*, there's just some bits for red, some bits for blue and some bits for green. YUV (a representation of YCbCr) should be the same, right? Well, only sort of.

Packed versus planar formats store the same data, they just store it differently in memory. Packed formats behave like RGB formats, where a Y' component is followed by Cb and Cr components. The order depends on the exact pixel format in use, but it just determines how the data is interleaved. \
Planar formats store the data in separate "planes" in memory, which is just a fancy way of saying the data is stored together. So there's be one linear list of all the Y' values in a frame, one of all the Cb and one of all the Cr. There's also semi-planar formats, which usually put the Cb and Cr together. Some formats also are tiled, but these are less common.

To summarize:

- Packed formats are interleaved.
- Planar formats have three lists of all the values, one for each component.
- Semi-planare formats have two lists, one for the luma (Y) and one for the chroma (interleaving Cb and Cr).

### Equivalent Formats

These formats are equivalent enough for the purposes of streaming.

4:4:4 8-bit colour: NV24/NV42, Y444, XRGB/XB24, BGR3, RGB3, Y444, YUV3\
4:2:2 8-bit colour: NV16/NV61, YUYV/UYVY/VYUY/YVYU, 422P\
4:2:0 8-bit colour: NV21/NV21, I420, YV12, YU12

There are also a few 10-bit formats in use. Mainly P010 (a semi-planar 4:2:0 YUV format) and RX30 (a 10-10-10 RGB format). 12-bit and 16-bit formats are rarely encountered in livestreaming.

### Alpha (Transparency)

Many of these formats have a version with an alpha (transparency channel), though these are mainly used internally for compositing and the like and are rarely produced by inputs or consumed by encoders, at least for the purposed of livestreaming.

## What About Bayer Formats?

No.
