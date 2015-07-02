
  . /etc/profile.d/qt5.rc   &&

  OPTS=+" -DQCA_INSTALL_IN_QT_PREFIX=ON" &&

  sedit "37i #include <QIODevice>" include/QtCrypto/qca_basic.h &&

  default_cmake_build 
