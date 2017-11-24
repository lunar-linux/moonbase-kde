
  . /etc/profile.d/qt5.rc &&

  sed -i 's|SUBDIRS  += Accounts tests|SUBDIRS += Accounts|' accounts-qt.pro &&

  /usr/lib/qt5/bin/qmake $OPTS &&

  default_make
