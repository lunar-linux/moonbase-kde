source /etc/profile.d/qt5.rc   &&

cmake -B build5 \
       -DCMAKE_BUILD_TYPE=Release \
       -DQT_MAJOR_VERSION=5 \
       -DBUILD_TESTING=OFF \
       -DCMAKE_SKIP_RPATH=ON &&
cmake --build build5

prepare_install &&
cmake --install build5 &&

if module_installed qt6-base; then
source /etc/profile.d/qt6.rc &&
cmake -B build6 \
    -DCMAKE_BUILD_TYPE=Release \
    -DQT_MAJOR_VERSION=6 \
    -DBUILD_TESTING=OFF \
    -DCMAKE_SKIP_RPATH=ON &&
cmake --build build6 &&
prepare_install &&
cmake --install build6
fi
