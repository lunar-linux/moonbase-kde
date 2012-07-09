(

  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  if [ ! -d /usr/lib/lunar/plugins ] ; then
    mkdir -p /usr/lib/lunar/plugins
  fi &&

  OPTS+=" -DMOZPLUGIN_INSTALL_DIR=/usr/lib/lunar/plugins" &&

  default_cmake_build
  
) > $C_FIFO 2>&1
