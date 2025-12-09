source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_TESTING=OFF \
        -Wno-dev \
        -DQT_MAJOR_VERSION=6 \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX"

cmake -B $MODULE-$VERSION $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
