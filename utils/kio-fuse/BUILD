source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DQT_MAJOR_VERSION=6 \
        -Wno-dev"


cmake -B build-$MODULE -S . $OPTS&&
cmake --build build-$MODULE &&

prepare_install &&
cmake --install build-$MODULE
