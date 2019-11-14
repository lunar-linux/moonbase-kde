. /etc/profile.d/qt5.rc &&

NINJAJOBS=${MAKES:+-j$MAKES} &&

mkdir build &&
cd    build &&

qmake .. -- -system-ffmpeg -webengine-icu &&

default_make &&

find $QT5DIR/ -name \*.prl \
   -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d' {} \;

