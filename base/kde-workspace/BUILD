
  sedit 's:/usr/share/hwdata/usb.ids:/usr/share/usb.ids:' kinfocenter/Modules/usbview/usbdb.cpp &&

  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

# We disable these to avoid conflicts with plasma
  OPTS+=" -DBUILD_systemsettings=0   \
          -DBUILD_powerdevil=0       \
          -DBUILD_kwin=0             \
          -DBUILD_ksysguard=0        \
          -DBUILD_kmenuedit=0        \
          -DBUILD_plasma=0           \
          -DBUILD_kinfocenter=0"     &&

  default_cmake_build
