. /etc/profile.d/qt5.rc &&

NINJAJOBS=${MAKES:+-j$MAKES} &&

mkdir build &&
cd    build &&

qmake .. -- -system-ffmpeg -webengine-icu -webengine-webrtc &&

default_make &&

find /usr/lib/qt5/ -type f -name 'libQt5WebEngine*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \;
