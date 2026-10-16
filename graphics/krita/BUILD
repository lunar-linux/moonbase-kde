source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DBUILD_KRITA_QT_DESIGNER_PLUGINS=ON \
        -DCMAKE_PREFIX_PATH=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DALLOW_UNSTABLE=QT6 \
        -DENABLE_UPDATERS=OFF \
        -DBUILD_TESTING=OFF \
        -DUSE_EXTERNAL_RAQM=OFF \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
