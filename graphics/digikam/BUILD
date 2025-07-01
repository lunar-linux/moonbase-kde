source /etc/profile.d/qt6.rc &&

export CMAKE_C_FLAGS="$CFLAGS -ffat-lto-objects -I/usr/include/Imath"
export CMAKE_CXX_FLAGS="$CXXFLAGS -ffat-lto-objects -I/usr/include/Imath"

OPTS+=" -DENABLE_AKONADICONTACTSUPPORT=ON \
        -DENABLE_KFILEMETADATASUPPORT=ON \
        -DENABLE_MEDIAPLAYER=ON \
        -DENABLE_APPSTYLES=ON \
        -DBUILD_WITH_QT6=ON   \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DENABLE_QWEBENGINE=ON" &&

if module_installed ccache ; then
  OPTS+=" -DBUILD_WITH_CCACHE=ON"
fi &&

default_cmake_build
