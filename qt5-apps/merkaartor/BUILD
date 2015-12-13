
  sedit "s:bool positionValid = FALSE:bool positionValid = false:" src/Docks/GeoImageDock.cpp &&
  sedit "12i #include <QDrag>" src/Docks/GeoImageDock.h &&

  . /etc/profile.d/qt5.rc &&

  /usr/lib/qt5/bin/qmake PREFIX=/usr     \
                         NODEBUG=1       \
                         RELEASE=1       \
                         SYSTEM_QUAZIP=1 \
                         ZBAR=0          \
                         Merkaartor.pro  \
                         $OPTS           &&

  default_make
