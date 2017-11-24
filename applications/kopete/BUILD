
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 -DQCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto" &&

# Prefer it look here instead of /usr/lib/mozilla/plugins
  OPTS+=" -DMOZPLUGIN_INSTALL_DIR=/usr/lib/lunar/plugins" &&
  default_cmake_build
