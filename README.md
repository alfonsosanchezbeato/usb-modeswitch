# abeato-usb-modeswtich snap

USB_ModeSwitch is (surprise!) a mode switching tool for controlling
'multi-mode' USB devices. See https://www.draisberghof.de/usb_modeswitch/ for
more details. Please find the source code for the snap at
https://github.com/alfonsosanchezbeato/usb-modeswitch.
Connect the interfaces, then run usb_modeswitch. For instace, for a
device that we want to switch from VID:PID 19d2:2000 to 19d2:0066:

    snap install abeato-usb-modeswitch
    snap connect abeato-usb-modeswitch:hardware-observe
    snap connect abeato-usb-modeswitch:raw-usb
    sudo abeato-usb-modeswitch.usb-modeswitch -v 19d2 -p 2000 -V 19d2 -P 0066 \
      -W -c /snap/abeato-usb-modeswitch/current/etc/usb_modeswitch.d/19d2:2000
