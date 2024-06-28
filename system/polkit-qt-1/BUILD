OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -Wno-dev"

if in_depends $MODULE qt5; then
  source /etc/profile.d/qt5.rc &&
  cmake -B polkit-qt5 -S . $OPTS &&
  cmake --build polkit-qt5
fi

source /etc/profile.d/qt6.rc &&
cmake -B polkit-qt6 -S . $OPTS -DQT_MAJOR_VERSION=6 &&
cmake --build polkit-qt6 &&

prepare_install &&

if in_depends $MODULE qt5; then
  cmake --install polkit-qt5
fi &&

cmake --install polkit-qt6
