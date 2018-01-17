  . /etc/profile.d/qt5.rc &&

  sedit 's:/qml:/lib/qt5/qml:' CMakeLists.txt &&

  OPTS+=" -DBUILD_EXAMPLES=0  \
          -DBUILD_TESTS=0"    &&

  default_cmake_build
