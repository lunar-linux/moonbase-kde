
  . /etc/profile.d/qt5.rc &&

  patch_it $SOURCE2 1 &&

  sedit "s:#include <QXmlStreamWriter>:#include <QXmlStreamWriter>\n#include <QDataStream>:" src/libkst/editablematrix.cpp src/libkst/editablevector.cpp &&
  sedit "39i #include <cmath>" src/libkstmath/curve.cpp &&
  cp -r cmake/pyKst/* pyKst/ &&

# It looks for 0.10.0 or greater for scipy, we have 0.17, something wonky
  sedit '38d' pyKst/CMakeLists.txt &&

  OPTS+=" -Dkst_release=1 \
          -Dkst_pch=OFF \
          -Dkst_qt5=ON    \
          -Dkst_rpath=OFF \
          -Dkst_svnversion=OFF \
          -Dkst_python=1 \
          -DPYTHON_EXECUTABLE=/usr/bin/python2.7 \
          -Dkst_python_prefix=/usr/lib/python2.7 \
          -Dkst_install_libdir=lib \
          -Dkst_install_prefix=/usr" &&

  default_cmake_build
