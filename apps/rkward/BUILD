source /etc/profile.d/qt6.rc &&

find -name index.docbook | xargs sed -e 's|" preview_custom"|"preview_custom"|' -i &&

OPTS+=" -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_PREFIX_PATH=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DQt6QmlCompilerPlusPrivate_DIR=/usr/lib/qt6/cmake/Qt6QmlCompiler \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

default_cmake_build
