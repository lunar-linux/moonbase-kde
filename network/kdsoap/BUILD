source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev \
        -DKDSoap_QT6=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt6/mkspecs/modules"

cmake -B $MODULE-qt6 -S . $OPTS &&
cmake --build $MODULE-qt6

prepare_install &&
cmake --install $MODULE-qt6
