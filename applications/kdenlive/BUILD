source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=RELEASE \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_OLDINCLUDEDIR=/usr/include/kdenlive \
        -Wno-dev"

cmake -B kdenlive-build -S . -G Ninja $OPTS &&
cmake --build kdenlive-build &&

prepare_install
cmake --install kdenlive-build
