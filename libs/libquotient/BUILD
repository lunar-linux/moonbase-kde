source /etc/profile.d/qt5.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -DQuotient_ENABLE_E2EE=ON -DBUILD_SHARED_LIBS=ON -Wno-dev"

cmake -B $MODULE-qt5 -S . $OPTS -DBUILD_WITH_QT6=OFF &&
cmake --build $MODULE-qt5 &&

if in_depends $MODULE qtkeychain-qt6; then
source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . $OPTS -DBUILD_WITH_QT6=ON &&
cmake --build $MODULE-qt6
fi &&

prepare_install &&

cmake --install $MODULE-qt5 &&

if module_installed qtkeychain-qt6; then
cmake --install $MODULE-qt6
fi
