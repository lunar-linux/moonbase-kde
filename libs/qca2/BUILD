  . /etc/profile.d/qt5.rc &&

  if in_depends $MODULE Botan ; then
   BOTAN_CFLAGS+=" -I`pkg-config --cflags /usr/lib/pkgconfig/botan-2.pc`"
  fi &&

  OPTS+=" -DBUILD_TESTS=0 \
          -DDQCA_INSTALL_IN_QT_PREFIX=1 \
          -DQCA_FEATURE_INSTALL_DIR=/usr/lib/qt5/mkspec/features \
          -DQCA_PLUGINS_INSTALL_DIR=/usr/lib/qt5/plugins" &&

  default_cmake_build
