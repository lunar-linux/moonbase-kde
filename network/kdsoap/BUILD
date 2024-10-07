export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release -Wno-dev"

if in_depends $MODULE qt5; then
source /etc/profile.d/qt5.rc &&
cmake -B $MODULE-qt5 -S . $OPTS -DKDSoap_QT6=OFF -DCMAKE_INSTALL_PREFIX=/usr &&
cmake --build $MODULE-qt5
fi &&

source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . $OPTS -DKDSoap_QT6=ON -DCMAKE_INSTALL_PREFIX=/usr -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt5/mkspecs/modules &&
cmake --build $MODULE-qt6

prepare_install &&

if in_depends $MODULE qt5; then
cmake --install $MODULE-qt5
fi &&

cmake --install $MODULE-qt6
