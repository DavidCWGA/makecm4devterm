# makecm4devterm
Modifies Raspberry Pi OS 64-bit images to work on the Clockwork DevTerm CM4.

## Requirements

This script needs to run on a 64-bit ARM machine. You can run it on a Raspberry Pi already running 64-bit Raspberry Pi OS, or Debian, or you can run it on a real ARM system running Debian, or in a virtual machine on an ARM system, such as an Apple Silicon Mac. The author runs it on Debian inside a "UTM" virtual machine on his Mac.

## Usage

Go to the "all download options" page at raspberry.com (at the time of writing, at https://www.raspberrypi.com/software/operating-systems/), find the 64-bit "Raspberry Pi OS with desktop" image, and copy the Download URL. (You can also download the image if you prefer, but do not decompress it.)

Run the script using the URL of the image, or the path of the downloaded image, as the first argument.

```
./makecm4devterm https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2023-05-03/2023-05-03-raspios-bullseye-arm64.img.xz
```

Or:

```
./makecm4devterm ~/Downloads/2023-05-03-raspios-bullseye-arm64.img.xz
```

When the script is complete, the path to the modified image will be displayed, which on most systems will be inside /tmp. Copy this image and/or write it to a Micro SD card using "dd".

## Bugs

After booting your DevTerm, if the printer doesn't show up as an available device, run:

```
sudo dpkg-reconfigure devterm-thermal-printer-cm4 devterm-thermal-printer-cups
```

This script is not guranteed to work on versions of Raspberry Pi OS based on Debian 12. At the time of writing, these don't exist yet.

David Glover-Aoki
david@gloveraoki.net
June 2023
