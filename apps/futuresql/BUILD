source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTING=OFF -Wno-dev -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX -DCMAKE_SKIP_RPATH=ON"

cmake -B $MODULE-qt6 -DQT_MAJOR_VERSION=6 $OPTS &&
cmake --build $MODULE-qt6 &&

prepare_install &&
cmake --install $MODULE-qt6
