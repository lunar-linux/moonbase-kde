
  . /etc/profile.d/qt5.rc &&

  sed -e 's/-Werror//' -i common-project-config.pri &&

  #qmake-qt5 ../$pkgname-*/$pkgname.pro PREFIX=/usr  

  qmake-qt5  PREFIX=/usr &&

  default_make
