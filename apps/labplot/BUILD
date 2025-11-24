source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DENABLE_LIBORIGIN=OFF \
        -DLOCAL_DBC_PARSER=OFF \
        -DLOCAL_VECTOR_BLF=OFF \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -Wno-dev"


cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
