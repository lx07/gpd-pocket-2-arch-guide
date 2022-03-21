# GPD Pocket 3 Xorg Fixes




### Create Pocket 2 Xorg configs

Create Intel xorg config at `/etc/X11/xorg.conf.d/20-intel.conf` with the following:

    Section "Device"
      Identifier    "Iris Xe Graphics"
      Driver        "intel"
      Option        "AccelMethod"            "sna"
      Option        "TearFree"               "true"
      Option        "DRI"                    "3"
    EndSection

Create display config at `/etc/X11/xorg.conf.d/30-display.conf` with the following:

    Section "Monitor"
      Identifier    "DPI1"
      Option        "Rotate"                 "right"
    EndSection

Create touchscreen config at `/etc/X11/xorg.conf.d/99-touchscreen.conf` with the following:

    Section "InputClass"
      Identifier    "calibration"
      MatchProduct  "GXTP7380:00 27C6:0113"
      Option        "TransformationMatrix"   "0 1 0 -1 0 1 0 0 1"
    EndSection
