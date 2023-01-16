. /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DINSTALL_LIBEXECDIR=qt6 \
        -DINSTALL_LIBDIR=qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_SYSCONFDIR=/etc/xdg"

cmake -B build -S . -G Ninja $OPTS -Wno-dev &&
cmake --build build &&
prepare_install &&

# Remove point to the src build direcotry
find build/qt6 -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake -B build -S . -G Ninja $OPTS -Wno-dev &&
cmake --build build &&
prepare_install &&
cmake --install build
