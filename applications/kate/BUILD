source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

# With X-DBUS-StartupType=Multi kinit gets confused so we just set to none.
# Multiple files can still be opened within Kate, just eliminates the error popup.
sedit "s:X-DBUS-StartupType=Multi:X-DBUS-StartupType=None:" \
	 /usr/share/applications/org.kde.kate.desktop
