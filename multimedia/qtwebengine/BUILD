source /etc/profile.d/qt5.rc &&

if module_installed %KERBEROS ;then
  OPTS+=" -webengine-kerberos"
fi &&

mkdir build &&
cd    build &&

qmake-qt5 .. -- -system-ffmpeg -webp -proprietary-codecs -webengine-icu $OPTS &&

default_make &&

find /usr/lib/qt5/$MODULE -type f -name 'libQt5WebEngine*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \;
