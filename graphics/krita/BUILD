# Fix xsimd detection
#sedit 's:9 10 11:9 10 11 12:' CMakeLists.txt &&

source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'
#export CFLAGS+=" -fPIC"


OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DBUILD_KRITA_QT_DESIGNER_PLUGINS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
