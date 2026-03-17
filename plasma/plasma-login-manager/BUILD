source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDBUS_CONFIG_FILENAME=plasma_org.freedesktop.DisplayManager.conf \
        -DRUNTIME_DIR=/run/plasmalogin \
        -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DINSTALL_PAM_CONFIGURATION=OFF \
        -Wno-dev"


cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION &&

mkdir -p /etc/plasmalogin.conf.d &&
touch /etc/plasmalogin.conf &&

cp $SCRIPT_DIRECTORY/plasma* /etc/plasmalogin.conf.d/
