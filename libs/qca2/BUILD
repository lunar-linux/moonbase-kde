
  . /etc/profile.d/qt5.rc &&

  sed -i 's@ca-bundle.pem@ca-bundle.crt@g' CMakeLists.txt &&

  OPTS+=" -DQT4_BUILD=0 -DQCA_SUFFIX=qt5 -DBUILD_TESTS=0 -DQCA_INSTALL_IN_QT_PREFIX=1" &&

  default_cmake_build
