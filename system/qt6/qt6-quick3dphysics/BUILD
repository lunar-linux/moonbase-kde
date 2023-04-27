source /etc/profile.d/qt6.rc &&

#Generating .rcc/qmlcache/qtgraphicaleffectsplugin_ColorOverlay_qml.cpp
#Detected locale "en_US" with character encoding "ISO-8859-1", which is not UTF-8.
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DINSTALL_BINDIR=lib/qt6/bin \
        -DINSTALL_LIBEXECDIR=lib/qt6 \
        -DINSTALL_LIBDIR=lib/qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=/usr/lib/qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=lib/qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_SYSCONFDIR=/etc/xdg"

cmake -B build -S . -G Ninja $OPTS -Wno-dev &&
cmake --build build &&
prepare_install &&
cmake --install build
