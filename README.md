# FFmpeg - H3 - Armbian 5.23 (Cedrus HW Encoder - CMOS Camera)

FFmpeg 3.1.4 with built in Cedrus264 HW Encoder for the H3 platform.
This was built on Ubuntu 12.04 rootfs (Armbian 5.23).

Ideal for H3 boards with 512MB / 1GB Dram memory size
-----------------------------------------------------

- FriendlyArm (NanoPi M1 / NanoPi Neo Air)
- BananaPi M2+
- OPI


Dependencies
============

	sudo apt-get install libmp3lame-dev libx264-dev libpulse-dev libv4l-dev libva-dev


Source Code and Instructions
============================

https://github.com/linux-sunxi/libcedrus

https://github.com/uboborov/ffmpeg_h264_H3


How to use it
=============

- Attach you CMOS camera
- Clone the repo: git clone https://github.com/avafinger/ffmpeg_cedrus264_H3_Armbian_5.23.git
- cd ffmpeg_cedrus264_H3_Armbian_5.23
- Install the deb package: sudo dpkg -i ffmpeg-3.1.4_1.0-3.deb
- type: 

	sudo ffmpeg-3.1.4 -f v4l2 -channel 0 -video_size 1920x1080 -i /dev/video0 -pix_fmt nv12 -r 22 -c:v cedrus264 night_video_test4_1920x1080.mp4

- adjust the -r parameter and -qp for quality

Play the MP4 file with your preferred application


There is no problem installing this version over official version, they can coexist.

Limitations
===========
 * Read the author's note - POC
