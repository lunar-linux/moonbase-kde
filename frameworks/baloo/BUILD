source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION

#Baloo likes a large max-user-watches greater than 8192 #Instead #of
#fiddling with the 99-sysctl.conf, we will just make a new file just for that.
echo fs.inotify.max_user_watches=524288 > /etc/sysctl.d/40-max-user-watches.conf
