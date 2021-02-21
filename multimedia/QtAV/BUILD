  . /etc/profile.d/qt5.rc &&

  sedit 's:/qml:/lib/qt5/qml:' CMakeLists.txt &&

  OPTS+=" -DBUILD_EXAMPLES=OFF  \
          -DBUILD_QT5OPENGL=ON \
          -DBUILD_TESTS=OFF"    &&

  default_cmake_build
