  . /etc/profile.d/qt5.rc &&

  cp -r cmake/pyKst/* pyKst/ &&

# It looks for 0.10.0 or greater for scipy, we have 0.17, something wonky
  sedit '38d' pyKst/CMakeLists.txt &&

  OPTS+=" -Dkst_release=1 \
          -Dkst_pch=0 \
          -Dkst_3rdparty=0 \
          -Dkst_qt5=1    \
          -Dkst_rpath=0 \
          -Dkst_svnversion=0 \
          -Dkst_python=1 \
          -DPYTHON_EXECUTABLE=/usr/bin/python2.7 \
          -Dkst_python_prefix=/usr/lib/python2.7 \
          -Dkst_install_libdir=lib \
          -Dkst_install_prefix=/usr" &&

  default_cmake_build
