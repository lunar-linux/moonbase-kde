source /etc/profile.d/qt6.rc  &&

OPTS+=" -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S client $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
