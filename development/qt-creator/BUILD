source /etc/profile.d/qt6.rc &&
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr  \
        -DCMAKE_BUILD_TYPE=RELEASE   \
        -DCMAKE_INSTALL_LIBEXECDIR=lib \
        -DQTC_CLANG_BUILDMODE_MATCH=ON \
        -DHELPVIEWER_DEFAULT_BACKEND=qtwebengine \
        -DCLANGTOOLING_LINK_CLANG_DYLIB=ON \
        -DBUILD_DEVELOPER_DOCS=ON \
        -DWITH_DOCS=ON \
        -Wno-dev"

if module_installed ccache; then
  OPTS+=" -DWITH_CCACHE_SUPPORT=ON"
fi &&

cmake -B $MODULE -G Ninja $OPTS &&
cmake --build $MODULE &&

prepare_install &&
cmake --install $MODULE &&

# Desktop menu entry
cat > $MODULE.desktop << EOF &&
[Desktop Entry]
Type=Application
Name=Qt6 Creator
Comment=Qt6 based Development Tool
Exec=$QT6_DIR/bin/qtcreator
Icon=/usr/lib/share/icons/hicolor/256x256/apps/QtProject-qtcreator.png
Categories=Development;
EOF

install -D -m644 $MODULE.desktop /usr/share/applications/$MODULE.desktop
