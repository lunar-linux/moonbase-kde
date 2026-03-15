source /etc/profile.d/qt6.rc &&

OPTS+=" -DUBSAN=ON \
        -DTSAN=ON \
        -DBUILD_TESTING=OFF \
        -DENABLE_SYSTRAY_UNITY_BACKEND=NO \
        -DUPDATE_CHECK=OFF \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
