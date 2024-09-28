source /etc/profile.d/qt6.rc &&
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
        -DINSTALL_SYSCONFDIR=/etc/xdg \
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -Wno-dev"

cmake -B build -S . -G Ninja $OPTS &&
cmake --build build &&
prepare_install &&
cmake --install build
