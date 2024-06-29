export LANG='en_US.UTF-8'
OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTING=OFF -Wno-dev -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX"

if in_depends $MODULE qt5; then
source /etc/profile.d/qt5.rc &&
cmake -B $MODULE-qt5 -S . $OPTS &&
cmake --build $MODULE-qt5
fi &&

source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . -DQT_MAJOR_VERSION=6 $OPTS &&
cmake --build $MODULE-qt6 &&

prepare_install &&

if in_depends $MODULE qt5; then
cmake --install $MODULE-qt5
fi &&

cmake --install $MODULE-qt6
