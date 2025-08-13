source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DQUAZIP_QT_MAJOR_VERSION=6 \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev"

cmake -B build-qt6 -S . $OPTS &&
cmake --build build-qt6 &&

prepare_install &&
cmake --install build-qt6
