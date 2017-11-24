
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

  OPTS+=" -DWITH_ActiveApp=0 \
          -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 \
          -DQCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto" &&

  default_cmake_build
