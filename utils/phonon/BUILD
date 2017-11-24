export CFLAGS="$CFLAGS -fPIC" &&

if module_installed qt4; then
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  OPTS+=" -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake \
          -DPHONON_BUILD_PHONON4QT5=OFF \
          -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=ON" &&

  default_cmake_build &&
  make clean

  # needed by kde-baseapps, kipi-plugins, kmldonkey and possible other modules
  # ln -sf /usr/lib/libphonon.so.4  /usr/lib/qt4/libphonon.so
fi &&

#devoke_installwatch &&

if module_installed qt5; then
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON \
          -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=ON \
          -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake" &&

  default_cmake_build
fi
