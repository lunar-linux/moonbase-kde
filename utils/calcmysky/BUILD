source /etc/profile.d/qt6.rc  &&

OPTS+=" -DCMAKE_CXX_STANDARD=17 \
        -DCMAKE_CXX_COMPILER=g++ \
        -W no-dev \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCPM_LOCAL_PACKAGES_ONLY=ON \
        -DCMAKE_CXX_FLAGS=-fPIC \
        -DQT_VERSION=6"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION --target all &&

prepare_install &&
cmake --install $MODULE-$VERSION
