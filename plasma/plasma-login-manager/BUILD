source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDBUS_CONFIG_FILENAME=plasma_org.freedesktop.DisplayManager.conf \
        -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DINSTALL_PAM_CONFIGURATION=OFF \
        -Wno-dev"


cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

mkdir -p /etc/plasmalogin.conf.d
#touch /etc/plasmalogin.conf &&

cp data/pam/arch/plasma* /etc/pam.d/
sedit 's:auth        include     system-login:auth        include     system-auth:' /etc/pam.d/plasmalogin
sedit 's:account     include     system-login:account     include     system-auth:' /etc/pam.d/plasmalogin
sedit 's:password    include     system-login:password    include     system-auth:' /etc/pam.d/plasmalogin
sedit 's:session     include     system-login:session     include     system-auth:' /etc/pam.d/plasmalogin
#/usr/lib/pam.d/
