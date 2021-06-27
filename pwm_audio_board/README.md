# Raspberry Pi Audio board

## Description

This project is related to the Pi "Mac" blog post detailing the story behind.

## Details

The instructions below were successfully tested with the lates "Buster" revision of the Raspberry Pi OS.

## Instructions

1. Follow the build insructions from Chuck Gencon, "Making a Tiny Mac From a Raspberry Pi Zero", from <https://www.instructables.com/Making-a-Tiny-Mac-From-a-Raspberry-Pi-Zero/> until the sound/audio section
1. Build the audio board by Adafruit from <https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero>.
1. Solder the GPIO 18, 19 and Ground pin of the Raspberry PiZero W to the audio board.
1. Update your version of your Raspberry Pi OS to the latest "Buster" version:
`sudo apt-get update && sudo apt full-upgrade`
1. Modify the `/boot/config.txt`file to:

    - add the following : `dtoverlay=audremap,pins_18_19`
    - enable the line : `dtparam=audio=on` , in case it is disabled
1. Reboot the Pi and then connect to a terminal / ssh session
    - At this stage you should "see" the screen reacting now
1. Enter the `sudo raspi-config` application to ensure that the following option is selected:

    - Systems Options > Audio > Headphones
1. Also, you can deactivate Bluetooth to gain a bit more resources:

    1. First, deactivate it from the bluetooth menu on the top of the screen
    1. Then enter the following at the end of the `/boot/config.txt`
        - `dtoverlay=disable-bt`

