source /etc/profile.d/qt5.rc &&

export CFLAGS="${CFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"
export CXXFLAGS="${CXXFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"

export CFLAGS="-I/usr/include/pipewire-0.3"

if module_installed %KERBEROS ;then
  OPTS+=" -webengine-kerberos"
fi &&

mkdir -p $MODULE-$VERSION &&
cd    $MODULE-$VERSION &&

qmake-qt5 .. -- -system-ffmpeg -webp -proprietary-codecs -webengine-icu -spellchecker $OPTS &&

default_make

find /usr/lib/qt5/ -type f -name 'libQt5WebEngine*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \;
