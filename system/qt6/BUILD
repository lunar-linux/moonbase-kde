# Yeah, our ls doesn't live there
sedit 's:bin/ls:usr/bin/ls:g' qtbase/src/corelib/CMakeLists.txt qtbase/src/corelib/global/global.pri qtbase/src/corelib/doc/snippets/code/src_corelib_io_qdir.cpp &&

# This needs to happen here since CFLAGS/CXXFLAGS/LDFLAGS is only loaded during BUILD

# No SSE2 for i686
if [[ 'arch' == "i686" ]]; then
  SSE2="-DFEATURE_sse2=OFF"
fi &&

OPTS+=" -DFEATURE_gui=ON \
        -DCMAKE_VERBOSE_MAKEFILE=ON \
        -DFEATURE_optimize_full=ON \
        -DQT_BUILD_EXAMPLES_BY_DEFAULT=OFF \
        -DQT_BUILD_TESTS_BY_DEFAULT=OFF \
        -DCMAKE_INSTALL_PREFIX=${MODULE_PREFIX} \
        -DINSTALL_SYSCONFDIR=/etc/xdg \
        -DINSTALL_LIBDIR=${MODULE_PREFIX}/lib/$MODULE \
        -DINSTALL_BINDIR=${MODULE_PREFIX}/lib/$MODULE/bin \
        -DINSTALL_LIBEXECDIR=${MODULE_PREFIX}/lib/$MODULE \
        -DINSTALL_DOCDIR=${MODULE_PREFIX}/share/doc/$MODULE \
        -DINSTALL_ARCHDATADIR=${MODULE_PREFIX}/lib/$MODULE \
        -DINSTALL_DATADIR=${MODULE_PREFIX}/share/$MODULE \
        -DINSTALL_INCLUDEDIR=${MODULE_PREFIX}/include/$MODULE \
        -DINSTALL_PLUGINSDIR=${MODULE_PREFIX}/lib/$MODULE/plugins \
        -DINSTALL_MKSPECSDIR=${MODULE_PREFIX}/lib/$MODULE/mkspecs \
        -DINSTALL_EXAMPLESDIR=${MODULE_PREFIX}/share/doc/$MODULE/examples \
        $SSE2" &&

# Early part of configure barks about using GNUMakefiles, not recommended and to use ninja
cmake $OPTS -G Ninja -B build &&
cd build &&
cmake --build . &&
prepare_install &&
cmake --install . &&

# Remove pointing to the src build directory files.
find /usr/lib/$MODULE -type f -name '*Qt6*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&
find /usr/lib/$MODULE -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cat > $MODULE.rc << EOF &&
export Qt6_DIR="${MODULE_PREFIX}"
export QT6_PLUGIN_PATH="\${Qt6_DIR}/lib/${MODULE}/plugins"
export XDG_DATA_DIRS="\${XDG_DATA_DIRS:-/usr/share}:/usr/share/$MODULE"
export PKG_CONFIG_PATH="\${Qt6_DIR}/lib/${MODULE}/pkgconfig:\${PKG_CONFIG_PATH}"
export PATH="\${Qt6_DIR}/lib/${MODULE}/bin:\${PATH}"
export CMAKE_PREFIX_PATH="\${Qt6_DIR}/lib/qt6/cmake:\${CMAKE_PREFIX_PATH}"
export RCC=${Qt5_DIR}/lib/qt6/bin/rcc
export MOC=${Qt5_DIR}/lib/qt6/bin/moc
export UIC=${Qt5_DIR}/lib/qt6/bin/uic
EOF

install -m644 ${MODULE}.rc /etc/profile.d/${MODULE}.rc
