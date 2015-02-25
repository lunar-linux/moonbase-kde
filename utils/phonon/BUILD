
  export CFLAGS="$CFLAGS -fPIC"  &&
  
  if module_installed qt4 ; then
    source /etc/profile.d/qt4.rc   &&
    source /etc/profile.d/kde4.rc  &&
    OPTS+=" -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=TRUE \
            -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake" &&
    default_cmake_build  &&
  # needed by kde-baseapps, kipi-plugins, kmldonkey and possible other modules
    ln -sf /usr/lib/libphonon.so.4  /usr/lib/qt4/libphonon.so
   fi &&

   make clean &&

   if module_installed qt5 ; then
      devoke_installwatch &&
      . /etc/profile.d/qt5.rc &&
      OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON \
              -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=TRUE \
              -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake" &&
      default_cmake_build
   fi
