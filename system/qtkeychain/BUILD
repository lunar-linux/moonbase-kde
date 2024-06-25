source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_LIBDIR=lib -DCMAKE_INSTALL_PREFIX=/usr -DKDE_INSTALL_USE_QT_SYS_PATHS=ON -DCMAKE_BUILD_TYPE=Release -Wno-dev"

cmake -B build-qt6 -S . -DBUILD_WITH_QT6=ON $OPTS &&
cmake --build build-qt6 &&

source /etc/profile.d/qt5.rc &&
cmake -B build-qt5 -S . $OPTS &&
cmake --build build-qt5

prepare_install &&
cmake --install build-qt5 &&
cmake --install build-qt6
