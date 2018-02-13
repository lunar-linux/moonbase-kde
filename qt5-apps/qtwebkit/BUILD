. /etc/profile.d/qt5.rc &&

mkdir -p build &&
cd build &&

/usr/lib/qt5/bin/qmake ../WebKit.pro $OPTS &&

default_make &&

mv -f /usr/lib/qt5/pkgconfig/Qt5WebKit* /usr/lib/pkgconfig/ &&
ln -sf /usr/lib/pkgconfig/Qt5WebKit*.pc /usr/lib/qt5/pkgconfig/
