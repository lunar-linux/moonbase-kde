source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

mkdir -p /var/lib/plasmalogin &&
add_priv_group plasmalogin &&
add_priv_user plasmalogin -d /var/lib/plasmalogin -g plasmalogin &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDBUS_CONFIG_FILENAME=plasmalogin_org.freedesktop.DisplayManager.conf \
        -DINSTALL_PAM_CONFIGURATION=OFF \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

cp $SCRIPT_DIRECTORY/plasmalogin.conf /etc/ &&
cp $SCRIPT_DIRECTORY/plasmalogin $SCRIPT_DIRECTORY/plasmalogin-autologin $SCRIPT_DIRECTORY/plasmalogin-greeter /etc/pam.d/
