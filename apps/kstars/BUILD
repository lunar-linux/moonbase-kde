source /etc/profile.d/qt6.rc &&

export DCMAKE_C_FLAGS="$CFLAGS -ffat-lto-objects" \
export DCMAKE_CXX_FLAGS="$CXXFLAGS -ffat-lto-objects"

OPTS+=" -DBUILD_QT5=OFF -DCMAKE_DISABLE_FIND_PACKAGE_LibXISF=ON -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

default_cmake_build
