source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -Wno-dev -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

cmake -B build-qt6 -S . -DBUILD_QT5=OFF $OPTS&&
cmake --build build-qt6 &&

prepare_install &&

cmake --install build-qt6
