
  . /etc/profile.d/qt4.rc &&

  patch_it $SOURCE2 1 &&

  sedit "39i #include <cmath>" src/libkstmath/curve.cpp &&

  OPTS+=" -Dkst_release=1 \
          -Dkst_install_libdir=lib \
          -Dkst_install_prefix=/usr" &&
  default_cmake_build
