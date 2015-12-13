
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

  sedit "s:QtCrypto:Qca-qt4/QtCrypto/QtCrypto:" src/util/sha1hashgen.cpp &&
  OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 QCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto" &&

  default_cmake_build
