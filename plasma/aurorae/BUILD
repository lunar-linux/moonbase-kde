source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -Wno-dev -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

cmake -B build-$MODULE -S . -G Ninja $OPTS&&
cmake --build build-$MODULE &&

prepare_install &&
cmake --install build-$MODULE
