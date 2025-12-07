source /etc/profile.d/qt6.rc &&
export LDFLAGS=" -lzstd -liberty -lz -ldl -lsframe"
export LANG='en_US.UTF-8'

#If not specify Release it thinks it is using debug and make will fail
  OPTS+=" -DCMAKE_BUILD_TYPE=Release     \
          -DTULIP_BUILD_DOC=OFF          \
          -DTULIP_USE_QT6=ON             \
          -DTULIP_USE_CCACHE=ON          \
          -DBUILD_SHARED_LIBS=ON         \
          -DTULIP_BUILD_PYTHON_COMPONENTS=ON" &&

default_cmake_build
