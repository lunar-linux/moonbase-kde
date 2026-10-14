source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DBUILD_TESTING=OFF \
        -Wno-dev "

#-DQT_MAJOR_VERSION=6 \
cmake -B build -S . $OPTS &&
cmake --build build &&

prepare_install &&
cmake --install build
