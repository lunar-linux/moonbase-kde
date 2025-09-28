#The .clang-format file already exists.  Please remove it in order to use
#the file provided by ECM
rm .clang-format &&

source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_WITH_QT6=ON \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DKDE_INSTALL_INCLUDEDIR=include \
        -DKDE_INSTALL_BINDIR=bin \
        -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_LIBDIR=lib
        -DKF_SKIP_PO_PROCESSING=ON \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
