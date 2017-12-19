
  . /etc/profile.d/qt5.rc &&

  patch_it $SOURCE2 1 &&

  sedit "s:#include <QXmlStreamWriter>:#include <QXmlStreamWriter>\n#include <QDataStream>:" src/libkst/editablematrix.cpp src/libkst/editablevector.cpp &&
  sedit "39i #include <cmath>" src/libkstmath/curve.cpp &&

  OPTS+=" -Dkst_release=1 \
          -Dkst_pch=OFF \
          -Dkst_qt5=ON    \
          -Dkst_rpath=OFF \
          -Dkst_svnversion=OFF \
          -Dkst_install_libdir=lib \
          -Dkst_install_prefix=/usr" &&

  default_cmake_build
