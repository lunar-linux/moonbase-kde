  . /etc/profile.d/qt5.rc &&

  sed -i 's@ca-bundle.pem@ca-bundle.crt@g' CMakeLists.txt &&

  if in_depends $MODULE Botan ; then
   BOTAN_CFLAGS+=" -I`pkg-config --cflags /usr/lib/pkgconfig/botan-2.pc`"
  fi &&

  OPTS+=" -DQT4_BUILD=0 -DBUILD_TESTS=0 -DQCA_FEATURE_INSTALL_DIR=/usr/lib/qt5/mkspec/features/ " &&

  default_cmake_build
