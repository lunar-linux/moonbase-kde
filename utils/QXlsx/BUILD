source /etc/profile.d/qt6.rc &&

cd $MODULE &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_BUILD_TYPE=Release \
        -DQT_VERSION_MAJOR=6 \
        -DBUILD_SHARED_LIBS=ON \
        -Wno-dev "


cmake -B build -S . $OPTS &&
cmake --build build &&

prepare_install &&
cmake --install build
