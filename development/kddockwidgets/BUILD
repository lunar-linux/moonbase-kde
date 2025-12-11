source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DKDDockWidgets_FRONTENDS='qtwidgets;qtquick' \
        -DKDDockWidgets_QT6=true \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&

cmake --install $MODULE-$VERSION
