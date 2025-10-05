source /etc/profile.d/qt6.rc &&

export DCMAKE_C_FLAGS="$CFLAGS -ffat-lto-objects"
export DCMAKE_CXX_FLAGS="$CXXFLAGS -ffat-lto-objects"

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_DISABLE_FIND_PACKAGE_LibXISF=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DBUILD_TESTING=OFF \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
