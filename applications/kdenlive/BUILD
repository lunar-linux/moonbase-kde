source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

if module_installed ccache; then
  OPTS+=" -DCMAKE_CXX_COMPILER_LAUNCHER=ccache"
fi &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_OLDINCLUDEDIR=/usr/include/kdenlive \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_RUN_QMLLINT=OFF \
        -DBUILD_TESTING=OFF \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
