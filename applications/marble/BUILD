source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

sedit '52i Exec=/usr/bin/marble' src/plugins/runner/kml/marble_thumbnail_kmz.desktop &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_MARBLE_TOOLS=ON         \
        -DBUILD_MARBLE_EXAMPLES=OFF     \
        -DBUILD_MARBLE_TESTS=OFF        \
        -DBUILD_WITH_QT6=ON \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
