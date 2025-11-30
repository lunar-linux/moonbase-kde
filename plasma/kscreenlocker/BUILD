source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBEXECDIR=/usr/lib \
        -DKDE_INSTALL_INCLUDEDIR=include \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION &&

install -Dm644 $SCRIPT_DIRECTORY/kde.pam /usr/lib/pam.d/kde &&
install -Dm644 $SCRIPT_DIRECTORY/kde-fingerprint.pam /usr/lib/pam.d/kde-fingerprint &&
install -Dm644 $SCRIPT_DIRECTORY/kde-smartcard.pam /usr/lib/pam.d/kde-smartcard
