
  . /etc/profile.d/qt5.rc &&

  sed -i 's@ca-bundle.pem@ca-bundle.crt@g' CMakeLists.txt &&

  OPTS+=" -DQT4_BUILD=0 -DBUILD_TESTS=0 -DQCA_FEATURE_INSTALL_DIR=/usr/lib/qt5/mkspec/features/ " &&

  default_cmake_build
