sedit 's:/bin/ls:/usr/bin/ls:g' src/corelib/CMakeLists.txt util/cmake/tests/data/quoted.pro &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DFEATURE_optimize_full=ON  \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DINSTALL_BINDIR=qt6/bin \
        -DINSTALL_LIBDIR=qt6 \
        -DINSTALL_LIBEXECDIR=qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_TRANSLATIONSDIR=share/doc/translations \
        -DINSTALL_SYSCONFDIR=/etc/xdg/qt6 \
        -DQT_FEATURE_system_xcb_xinput=ON \
        -DCMAKE_INTERPROCEDURAL_OPTIMIZATION=ON \
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -DFEATURE_mtdev=OFF"

cmake -B build -S . -G Ninja $OPTS -Wno-dev &&
cmake --build build &&
prepare_install &&

#These installed by qt6-base get overwritten by those from othet qt6-x modules
#So delete these and let the others have their way
rm -f build/qt6/*.prl &&

cmake --install build 

cat > qt6.rc << EOF &&
  export QT6_DIR="${MODULE_PREFIX}"
  export QT6_PLUGIN_PATH="\${QT6_DIR}/qt6/plugins"
  export XDG_DATA_DIRS="\${XDG_DATA_DIRS:-/usr/share}:/usr/share/qt6"
  export PKG_CONFIG_PATH="\${QT6_DIR}/qt6/pkgconfig:\${PKG_CONFIG_PATH}"
  export PATH="\${QT6_DIR}/qt6/bin:\${PATH}"
  export CMAKE_PREFIX_PATH="\${QT6_DIR}/qt6/cmake:\${CMAKE_PREFIX_PATH}"
  export RCC_QT6="\${QT6_DIR}/qt6/rcc"
  export MOC_QT6="\${QT6_DIR}/qt6/moc"
  export UIC_QT6="\${QT6_DIR}/qt6/uic"
EOF

install -m644 qt6.rc /etc/profile.d/qt6.rc
