source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

# Boolean values required, mostly.
OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_LIBDIR=/usr/lib \
        -DCMAKE_INSTALL_SYSCONFDIR=/etc  \
        -DUSE_SYSTEM_LIBS=1 \
        -DSYSTEM_LIBS_REQUIRED=1 \
        -DINSTALL_HICOLOR_ICONS=1 \
        -DDISABLE_UPDATE_CHECK=1 \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
