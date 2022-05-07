. /etc/profile.d/qt5.rc &&

# So it doesn't stomp on qt5
mkdir -p /usr/lib/qt5/pkgconfig/$MODULE &&

OPTS+=" -DECM_PKGCONFIG_INSTALL_DIR=/usr/lib/qt5/pkgconfig/qtwebkit -DUSE_MINIMAL_DEBUG_INFO=ON" &&

default_cmake_build &&

ln -sf /usr/lib/qt5/pkgconfig/qtwebkit/Qt5WebKit.pc /usr/lib/pkgconfig/ &&
ln -sf /usr/lib/qt5/pkgconfig/qtwebkit/Qt5WebKitWidgets.pc /usr/lib/pkgconfig/
