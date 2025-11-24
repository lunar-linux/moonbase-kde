source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

export CMAKE_C_FLAGS="$CFLAGS -ffat-lto-objects -I/usr/include/Imath"
export CMAKE_CXX_FLAGS="$CXXFLAGS -ffat-lto-objects -I/usr/include/Imath"

OPTS+=" -DENABLE_AKONADICONTACTSUPPORT=ON \
        -DENABLE_KFILEMETADATASUPPORT=ON \
        -DENABLE_MEDIAPLAYER=ON \
        -DENABLE_APPSTYLES=ON \
        -DBUILD_WITH_QT6=ON   \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DENABLE_QWEBENGINE=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
