
  . /etc/profile.d/qt4.rc &&

  sedit "s:QtCrypto:Qca-qt4/QtCrypto/QtCrypto:" src/interface.h src/interface.cpp &&
  sedit "s:tests::" qoauth.pro &&

  qmake qoauth.pro &&

  default_make
