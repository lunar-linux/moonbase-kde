source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DBUILD_WITH_QT6=ON \
        -Wno-dev"


cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&

cmake --install $MODULE-$VERSION
