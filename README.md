## OpenIPC Install ##    

#### February 12th, 2018 ####

#### Version 0.2.3

#### https://openip.cam ####


### Full Disclosure ###

    - OpenIPC is forked from fang-hacks and is based on a proprietary Xiaomi firmware (FIRMWARE_660R.bin) with implementations allowing the end user to take full control of their Wyze camera.
    - At this time OpenIPC is not a 100% completely open source project as we rely upon the chinese base firmware at the moment to execute our payload (install method).
    - We do not have intentions to rewrite low level boot code and drivers for this camera model, instead we provide end users the ability to mitigate risk by gaining full root control.
    - Source code repositories for all added binaries will be added to the project shortly (snx_rtsp_server/dropbear). The inherent risk of a chinese base firmware can now be fully mitigated.

### Installation Instructions: ###


1. Download and install [Etcher](https://etcher.io) or [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/)

2. Write the openipc_v0.2.3.img to your SDcard

3. Open the SDCard and edit the files .wifissid and .wifipasswd to match your network

4. Flash the firmware to the camera:


    - Hold down the setup button for 10 seconds BEFORE connecting power
    - With button still depressed, plug in power to the camera while continuing to hold for another 10 - 12 seconds.
    - Release the button when the connection light blinks continually.
    - Press the button again and you should hear a Chinese voice prompt if successful.


5. Remove SDcard and reboot camera and reinsert after boot until you hear "click click".

6. Repeat Step 5 until you hear "click click".

7. Run openipscan.sh or openipscanwin.sh if you're on windows/mac and find the IP address of your new OpenIP Camera. Note: MAC address will be changed to c0:6d:1a*

8. Proceed to the status web page and apply the hacks. http://[discoveredipaddress]/cgi-bin/status 

NOTE: of you get a 404 error with a flashing blue led, Remove the sdcard and reinsert it. Shortly after thst the camera will go "click click" again. Proceed to the link now



Congratulations! Welcome to OpenIPC.

### Upgrade existing OpenIPC Install: ###

1. Download and install [Etcher](https://etcher.io) or [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/)

2. Write the openipc_v0.2.3.img to your SDcard

3. Open the SDCard and edit the files .wifissid and .wifipasswd to match your network

4. Reboot camera and reinsert SDcard after boot until you hear "click click".


### Connection Details: ###

    - RTSP: rtsp://[discoveredipaddress]/unicast Port 554
    - SSH: root/ismart12 Port 22


### Changelog: ###
#### Version 0.2.3 ####

    - Added Audio on RTSP control to Web interface
    - Updated README for more clear instructions


#### Contributions: ####

    - BTC: 3ByqQ73Sd6ykMm4JBzr4qoUt9Twtsm2ZBu

    - LTC: LLgajqD8QMfib58RDHu141sZy4qdJ9skRu

    - LSK: 7678123823745141779L

    - XMR: 45mwzBGAXqMPTZDCKPq1ySEbGiKUJohWd3FyeC1HqqBag33eXUeVsKuC65ZJ9ttEenSyTHf7kzRvCSoUtvx3sqkoJPVNRKg

Thanks to [samtap](https://github.com/samtap/) for [fanghacks](https://github.com/samtap/fanghacks) used as the base for OpenIPC. Thanks to [joeand37](https://github.com/joeand37) for inspiration. Thanks to the various other developers on the fanghacks page who cross-compiled some of the binaries.

#### Notable Changes from fang-hacks ####

    - Roadmap for OpenIPC Fork
    - Wifi setup via SDcard script
    - Includes downgrade firmware
    - Audio on RTSP as a toggle option
    - Includes rtsp scanner and openipc scanner

#### Build release image with dd ####
    - dd if=/dev/sdx of=~/openipc_v0.2.x.img bs=1 count=262144000
