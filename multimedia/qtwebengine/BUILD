. /etc/profile.d/qt5.rc &&

# So its prl files do not conflict with those provided by qt5
mkdir -p /usr/lib/qt5/$MODULE &&
OPTS+=" -libdir /usr/lib/qt5/$MODULE" &&

mkdir build &&
cd    build &&

qmake .. -- -system-ffmpeg -webengine-kerberos -proprietary-codecs -webengine-icu -webengine-webrtc -webp -spellchecker &&

default_make &&

find /usr/lib/qt5/$MODULE -type f -name 'libQt5WebEngine*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \;
