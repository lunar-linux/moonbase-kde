source /etc/profile.d/qt5.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX -DKDE_INSTALL_USE_QT_SYS_PATHS=ON -Wno-dev"

cmake -B $MODULE-qt5 -S . $OPTS -DPHONON_BUILD_QT6=OFF &&
cmake --build $MODULE-qt5 &&

source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . $OPTS -DPHONON_BUILD_QT5=OFF &&
cmake --build $MODULE-qt6 &&

prepare_install &&

cmake --install $MODULE-qt5 &&
cmake --install $MODULE-qt6
