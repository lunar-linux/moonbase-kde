unset CFLAGS CXXFLAGS
source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_VERBOSE_MAKEFILE=ON \
        -DBUILD_TESTING=OFF \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . $OPTS &&
#sedit 's:src/src:src:' $MODULE-$VERSION/src/CMakeFiles/spectacle_autogen.dir/AutogenInfo.json &&

cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
