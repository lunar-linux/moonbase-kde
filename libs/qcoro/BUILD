source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=ON \
        -DUSE_QT_VERSION=6 \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt6/mkspecs/modules/ \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
