source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DKDDockWidgets_FRONTENDS='qtwidgets;qtquick' \
        -DCMAKE_INSTALL_LIBDIR=lib \
        -DKDDockWidgets_QT6=true \
        -DECM_MKSPECS_INSTALL_DIR=/usr/qt6/mkspecs \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&

cmake --install $MODULE-$VERSION
