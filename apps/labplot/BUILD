source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DENABLE_LIBORIGIN=OFF \
        -DLOCAL_DBC_PARSER=OFF \
        -DLOCAL_VECTOR_BLF=OFF \
        -DBUILD_STATIC=OFF \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -Wno-dev"

default_cmake_build
  
