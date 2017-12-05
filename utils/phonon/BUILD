export CFLAGS="$CFLAGS -fPIC" &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON \
          -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=ON \
          -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake" &&

  default_cmake_build
