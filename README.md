# wtfos_custom_osd
custom icons for built in OSD elements

https://www.youtube.com/watch?v=id1x1TmzqIM&list=PLgZo1zkly1HN10JCDupFsE9PYG_iiSsH8&index=1&t=933s
https://github.com/EVilm1/WIKI-HACK-DJI-OSD

https://dl.google.com/android/repository/platform-tools-latest-windows.zip

set Path=%Path%;c:\temp\platform-tools\
### start adb
```
adb start-server
adb devices
```
### get original xml layout file
```
adb pull /system/gui/xml/racing_chnl_osd_win.xml [destination]
```
### copy updated xml layout to system
```
adb push racing_chnl_osd_win.xml /system/gui/xml/
adb push SDCard-Glasses-normal.png /system/gui/image/
adb push SDCard-Glasses-none.png /system/gui/image/
adb push SDCard-flight-normal.png /system/gui/image/
adb push SDCard-flight-none.png /system/gui/image/
adb push basic_img_rec_glasses.png /system/gui/image/
adb push basic_img_rec_glasses_none.png /system/gui/image/
adb push basic_img_rec_aircraft.png /system/gui/image/
adb push basic_img_rec_aircraft_none.png /system/gui/image/
adb push osd_ic_aircraftchannel.png /system/gui/image/
adb push osd_ic_audience.png /system/gui/image/
adb push osd_ic_aircraftbattery_normal.png /system/gui/image/
adb push osd_ic_aircraftbattery_low.png /system/gui/image/
adb push osd_ic_clock.png /system/gui/image/
adb push osd_ic_glassesbattery_normal.png /system/gui/image/
adb push osd_ic_glassesbattery_low.png /system/gui/image/
```
### copy conthrax font to system
```
adb push conthrax-sb.ttf /system/fonts/
```
### push fonts to goggles
```
adb -d push ./fonts/. /blackbox/wtfos/opt/fonts
```
### stop adb
```
adb disconnect
adb kill-server
```
Soft restart goggles V1: adb  shell "/opt/bin/killall -KILL dji_glasses_original"

Soft restart goggles V2: adb  shell "/opt/bin/killall -KILL dji_gls_wm150_original"

python.exe show_xml.py -i racing_chnl_osd_win.xml

