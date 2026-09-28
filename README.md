# panel-mipi-dbi-firmwares-and-overlays
firmware and device tree overlays for different displays for the panel-mipi-dbi driver  
The firmware files should go to the /lib/firmware directory  
if the "panel-mipi-dbi" kernel module is loaded at the initramfs stage, then the firmware should also be in initramfs  
adding device tree overlays depends on the build system and/or distribution you are using  
please note that the "panel-mipi-dbi" module may not load itself via udev if there is an overlay, and it may need to be added to the startup forcibly  

## "panel-mipi-dbi" firmware compiler
### install
```
git clone https://github.com/notro/panel-mipi-dbi.git
cd panel-mipi-dbi
```
### use
```
./mipi-dbi-cmd st7796_320x480.bin st7796_320x480.txt
```

## "device-tree-compiler" firmware compiler
### install
```
sudo apt install device-tree-compiler
```
### use
```
dtc -@ -I dts -O dtb -o st7796_320_480.dtbo st7796_320_480.dtso
```

## you may also be interested in the following projects
* https://github.com/igorkll/syslbuild
* https://github.com/igorkll/orangepi-zero3-st7735-devicetree-overlay
