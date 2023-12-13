# Fix xsimd detection
sedit 's:9 10 11:9 10 11 12:' CMakeLists.txt &&

. /etc/profile.d/qt5.rc &&

export CFLAGS+=" -fPIC"

OPTS+=" -DBUILD_KRITA_QT_DESIGNER_PLUGINS=ON"

default_cmake_build
