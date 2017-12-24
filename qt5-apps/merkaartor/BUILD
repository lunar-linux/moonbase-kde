
  sedit "s:#include <QtGui>:#include <QtGui>\n#include <QtNetwork>:" src/MainWindow.cpp &&
  sedit "s:#include <quazip:#include <quazip5:g" src/Tools/ZipEngine.h &&
  sedit "s:-lquazip:-lquazip5:" src/src.pro &&


  . /etc/profile.d/qt5.rc &&

  /usr/lib/qt5/bin/qmake PREFIX=/usr     \
                         NODEBUG=1       \
                         RELEASE=1       \
                         SYSTEM_QUAZIP=1 \
                         ZBAR=0          \
                         Merkaartor.pro  \
                         $OPTS           &&

  default_make
