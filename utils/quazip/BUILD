source /etc/profile.d/qt5.rc &&

cmake -B build-qt5 -S . -DCMAKE_INSTALL_PREFIX=/usr &&
cmake --build build-qt5 &&

prepare_install &&
cmake --install build-qt5
