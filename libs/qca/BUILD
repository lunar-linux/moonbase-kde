source /etc/profile.d/qt5.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_TESTS=OFF \
        -Wno-dev \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_BUILD_TYPE=Release \
        -DQCA_INSTALL_IN_QT_PREFIX=ON"

cmake -B $MODULE-qt5 -S . -G Ninja $OPTS -DBUILD_WITH_QT6=OFF &&
cmake --build $MODULE-qt5 &&

source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S . -G Ninja $OPTS -DBUILD_WITH_QT6=ON &&
cmake --build $MODULE-qt6 &&

prepare_install &&
cmake --install $MODULE-qt5 &&
cmake --install $MODULE-qt6
