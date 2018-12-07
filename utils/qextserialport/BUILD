# Don't need this prl's, they will overwrite those provided by Qt5 and contain the
# information.
  sedit 's:CONFIG += create_prl:#CONFIG += create_prl:' qextserialport.pro &&
  sedit 's|# linux*:CONFI| linux*:CONFI|' qextserialport.pro &&

  mkdir build && cd build &&
  /usr/lib/qt5/bin/qmake $OPTS .. &&

  default_make
