ource /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_WITH_QT6=ON \
        -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
