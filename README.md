## About

This is a set of GStreamer plugins about graphics/camera for rockchip platform.<br>
Most of them were modified based on upstream existing plugin.

This software has been tested only with kernel after 4.4.

## Status

| Elements       | Type  |  Comments  | origin |
| :----:  | :----:  | :----:  |
| rkximagesink    | Video Render (sink) |   kmssink on X11, for overlay display | ximagesink + kmssink |
| kmssink        |   Video Render (sink)   |  for overlay display   | Customized [kmssink](https://github.com/GStreamer/gst-plugins-bad/tree/master/sys/kms) |
| rgaconvert       |    Video Converter   |  for video colorspace,format,size conversion  | |
| ~~rgacomposite~~ | Video Compositing | Video compoiste | [v4l2 transform](https://github.com/GStreamer/gst-plugins-good/blob/master/sys/v4l2/gstv4l2transform.c) |
| ~~ispsrc~~        |    Device Sources  |  for rockchip isp driver  | [v4l2src](https://gstreamer.freedesktop.org/data/doc/gstreamer/head/gst-plugins-good/html/gst-plugins-good-plugins-v4l2src.html) |

## Usage

### rkximagesink
[Pipeline example](https://github.com/rockchip-linux/rk-rootfs-build/blob/master/overlay-debug/usr/local/bin/test_dec-gst.sh)

### rgaconvert
[Pipeline example](https://github.com/rockchip-linux/rk-rootfs-build/blob/master/overlay-debug/usr/local/bin/test_rga.sh)

Most of the sink pad properties are the same as that of v4l2 transform:
* `rotation` : 90-degree step rotation mode for the inner video frame : (optional)
* `hflip` : horizontal flip : (optional)
* `vflip` : vertical flip : (optional)
* `input-crop` : [Selection-crop](https://01.org/linuxgraphics/gfx-docs/drm/media/uapi/v4l/selection-api-003.html), should be left:right:width:height: (optional)
* `output-crop` : [Selection-compose](https://01.org/linuxgraphics/gfx-docs/drm/media/uapi/v4l/selection-api-003.html), should be left:right:width:height : (optional) 

### ispsrc
[Pipeline example](https://github.com/rockchip-linux/rk-rootfs-build/blob/master/overlay-debug/usr/local/bin/test_camera.sh)