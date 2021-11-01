cmake -G Ninja -B . \
        -DCMAKE_BUILD_TYPE=Release \
        -DFEATURE_optimize_full=ON  \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DINSTALL_BINDIR=lib/qt6/bin \
        -DINSTALL_LIBEXECDIR=/usr/lib/qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=/usr/lib/qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=lib/qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_SYSCONFDIR=/etc/xdg \
        $OPTS &&

cmake --build . &&
prepare_install &&
cmake --install . &&

# Remove pointing to the src build directory files.
find /usr/lib/$MODULE -type f -name '*Qt6*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&
find /usr/lib/$MODULE -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&
find /usr/lib/ -type f -name '*Qt6*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&
find /usr/lib/ -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cat > $MODULE.rc << EOF &&
  export Qt6_DIR="${MODULE_PREFIX}"
  export QT6_PLUGIN_PATH="\${Qt6_DIR}/lib/${MODULE}/plugins"
  export XDG_DATA_DIRS="\${XDG_DATA_DIRS:-/usr/share}:/usr/share/$MODULE"
  export PKG_CONFIG_PATH="\${Qt6_DIR}/lib/${MODULE}/pkgconfig:\${PKG_CONFIG_PATH}"
  export PATH="\${Qt6_DIR}/lib/${MODULE}/bin:\${PATH}"
  export CMAKE_PREFIX_PATH="\${Qt6_DIR}/lib/qt6/cmake:\${CMAKE_PREFIX_PATH}"
  export RCC=${Qt6_DIR}/lib/qt6/bin/rcc
  export MOC=${Qt6_DIR}/lib/qt6/bin/moc
  export UIC=${Qt6_DIR}/lib/qt6/bin/uic
EOF

install -m644 ${MODULE}.rc /etc/profile.d/${MODULE}.rc
