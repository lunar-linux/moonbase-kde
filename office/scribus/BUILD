source /etc/profile.d/qt5.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -D2GEOM_BUILD_SHARED=ON \
        -Wno-dev \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DWANT_HEADERINSTALL=ON"

cmake -B $MODULE-$VERSION -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&
cmake --install $MODULE-$VERSION
