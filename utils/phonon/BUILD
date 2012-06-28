(

  export CFLAGS="$CFLAGS -fPIC"  &&

  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  default_cmake_build  &&

  # needed by kde-baseapps, kipi-plugins, kmldonkey and possible other modules
  ln -sf /usr/lib/libphonon.so.4  /usr/lib/qt4/libphonon.so

) > $C_FIFO 2>&1
