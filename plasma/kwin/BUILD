#The .clang-format file already exists.  Please remove it in order to use
#the file provided by ECM
rm .clang-format &&

source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_WITH_QT6=ON \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DKDE_INSTALL_INCLUDEDIR=include \
        -DKDE_INSTALL_BINDIR=bin \
        -DKDE_INSTALL_LIBDIR=lib"

cmake -B build-$MODULE -S . $OPTS&&
cmake --build build-$MODULE &&

prepare_install &&
cmake --install build-$MODULE
