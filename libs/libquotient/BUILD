source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release  \
        -DQuotient_ENABLE_E2EE=ON \
        -DBUILD_SHARED_LIBS=ON \
        -Wno-dev"

cmake -B $MODULE-qt6 -S . $OPTS &&
cmake --build $MODULE-qt6

prepare_install &&
cmake --install $MODULE-qt6
