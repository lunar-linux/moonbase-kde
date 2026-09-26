source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDBUS_CONFIG_FILENAME=plasma_org.freedesktop.DisplayManager.conf \
        -DINSTALL_PAM_CONFIGURATION=OFF \
        -DPLASMALOGIN_INITIAL_VT=7 \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

mkdir -p /etc/plasmalogin.d &&

cp data/pam/kde-linux/* /etc/pam.d/ &&

sedit 's:system-login:system-auth:g' /etc/pam.d/plasmalogin &&
sedit 's:system-auth:system-local-login:g' /etc/pam.d/plasmalogin-autologin

