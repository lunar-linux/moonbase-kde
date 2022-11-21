source /etc/profile.d/qt5.rc &&
cmake -B build-qt5 -S . -DCMAKE_INSTALL_PREFIX=/usr &&
cmake --build build-qt5 &&

source /etc/profile.d/qt6.rc &&
cmake -B build-qt6 -S . -DCMAKE_INSTALL_PREFIX=/usr -DQUAZIP_QT_MAJOR_VERSION=6 &&
cmake --build build-qt6 &&

prepare_install &&
cmake --install build-qt5 &&
cmake --install build-qt6
