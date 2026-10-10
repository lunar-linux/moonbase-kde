source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'


add_priv_group plasmalogin &&
add_priv_user plasmalogin -d /var/lib/plasmalogin -g plasmalogin &&
mkdir -p /var/lib/plasmalogin &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDBUS_CONFIG_FILENAME=plasmalogin_org.freedesktop.DisplayManager.conf \
        -DINSTALL_PAM_CONFIGURATION=OFF \
        -DPLASMALOGIN_INITIAL_VT=7 \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

mkdir -p /etc/plasmalogin.d &&
cp $SCRIPT_DIRECTORY/plasmalogin.conf /etc/plasmalogin.d/ &&
cp $SCRIPT_DIRECTORY/plasma* /etc/pam.d/

