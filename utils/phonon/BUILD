(

  export CFLAGS="$CFLAGS -fPIC"  &&

  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  OPTS+=" -DPHONON_INSTALL_QT_EXTENSIONS_INTO_SYSTEM_QT=TRUE" &&

  default_cmake_build  &&

  # needed by kde-baseapps, kipi-plugins, kmldonkey and possible other modules
  ln -sf /usr/lib/libphonon.so.4  /usr/lib/qt4/libphonon.so

) > $C_FIFO 2>&1
