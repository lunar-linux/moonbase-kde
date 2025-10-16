OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -Wno-dev"

source /etc/profile.d/qt6.rc &&
cmake -B polkit-qt6 -S . $OPTS -DQT_MAJOR_VERSION=6 &&
cmake --build polkit-qt6 &&

prepare_install &&
cmake --install polkit-qt6
