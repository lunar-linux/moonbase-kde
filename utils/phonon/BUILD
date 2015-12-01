

  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

  sedit "s:BSD_SOURCE:DEFAULT_SOURCE:g" cmake/FindPhononInternal.cmake &&

  export CFLAGS="$CFLAGS -fPIC"  &&

  OPTS+=" -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake  \
          -DPHONON_BUILD_PHONON4QT5=0           \
          -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=1" &&

  default_cmake_build  &&
  # needed by kde-baseapps, kipi-plugins, kmldonkey and possible other modules
#  ln -sf /usr/lib/libphonon.so.4  /usr/lib/qt4/libphonon.so

  make clean &&

  devoke_installwatch &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DPHONON_BUILD_PHONON4QT5=1 \
          -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=1 \
          -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake" &&

  default_cmake_build
