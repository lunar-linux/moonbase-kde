. /etc/profile.d/qt5.rc &&

OPTS+=" -DBUILD_tests=0 -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr"

cd extra/kipi-plugins/ &&
mkdir build &&

cd build &&
cmake ../ $OPTS &&
default_make
