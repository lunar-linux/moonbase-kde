source /etc/profile.d/qt6.rc &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DQT_MAJOR_VERSION=6 \
        -D-DCMAKE_INSTALL_LIBEXECDIR=lib \
        -Wno-dev"


cmake -B build-$MODULE -S . -G Ninja $OPTS&&
cmake --build build-$MODULE &&

prepare_install &&
cmake --install build-$MODULE
