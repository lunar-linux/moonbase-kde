. /etc/profile.d/qt5.rc &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -Wno-dev"

cmake -B $MODULE-qt5 -S . $OPTS -DKDSoap_QT6=OFF &&
cmake --build $MODULE-qt5 &&

if in_depends $MODULE qt6-networkauth; then
source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . $OPTS -DKDSoap_QT6=ON &&
cmake --build $MODULE-qt6
fi &&

prepare_install &&

cmake --install $MODULE-qt5 &&

if module_installed qt6-networkauth; then
cmake --install $MODULE-qt6
fi
