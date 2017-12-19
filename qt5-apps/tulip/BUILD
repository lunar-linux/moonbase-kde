
  . /etc/profile.d/qt5.rc &&

#If not specify Release it thinks it is using debug and make will fail
  OPTS+=" -DCMAKE_BUILD_TYPE=Release     \
          -DTULIP_BUILD_DOC=OFF          \
          -DTULIP_USE_QT5=ON             \
          -DTULIP_BUILD_PYTHON_COMPONENTS=OFF" &&

  default_cmake_build
