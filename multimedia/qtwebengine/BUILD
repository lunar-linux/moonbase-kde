. /etc/profile.d/qt5.rc &&


mkdir build &&
cd    build &&

qmake .. -- -system-ffmpeg -webengine-kerberos -proprietary-codecs -webengine-icu -webengine-webrtc -webp -spellchecker &&

default_make &&

find /usr/lib/qt5/ -type f -name 'libQt5WebEngine*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \;
