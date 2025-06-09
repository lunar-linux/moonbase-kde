source /etc/profile.d/qt5.rc &&

sed -e 's|WANT_CPP17|WANT_CPP20|g' -e 's|CMAKE_CXX_STANDARD 17|CMAKE_CXX_STANDARD 20|g' -i CMakeLists.txt &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DWANT_HEADERINSTALL=ON \
        -DWANT_CPP20=ON"

cmake -B $MODULE-$VERSION -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&
cmake --install $MODULE-$VERSION
