  . /etc/profile.d/qt5.rc &&

  sed -e 's|${CMAKE_ROOT}/Modules|${CMAKE_INSTALL_PREFIX}/lib/cmake/QuaZip|' -i CMakeLists.txt &&

  OPTS+=" -DBUILD_WITH_QT4=0 -DCMAKE_CXX_FLAGS=$CFLAGS -fPIC" &&

  default_cmake_build
