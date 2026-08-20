source /etc/profile.d/qt6.rc &&


#Generating .rcc/qmlcache/qtgraphicaleffectsplugin_ColorOverlay_qml.cpp
#Detected locale "en_US" with character encoding "ISO-8859-1", which is not UTF-8.
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

# This applies here as well; https://github.com/neovim/neovim/issues/2557
CFLAGS="-U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2"
CXXFLAGS="-U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2"

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
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -DINSTALL_SYSCONFDIR=/etc/xdg \
        -DQT_INSTALL_XDG_DESKTOP_ENTRIES=ON \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&

# Remove point to the src build direcotry
find $MODULE-$VERSION/qt6 -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake --install $MODULE-$VERSION &&

# Make symlinks so these desktop files show up in the menu
ln -sf /usr/lib/share/applications/assistant.desktop /usr/share/applications/assistant.desktop &&
ln -sf /usr/lib/bin/assistant6 /usr/bin/assistant6 &&
ln -sf /usr/lib/share/icons/hicolor/128x128/apps/assistant.png /usr/share/pixmaps/assistant.png &&
ln -sf /usr/lib/share/applications/designer.desktop /usr/share/applications/designer.desktop &&
ln -sf /usr/lib/bin/designer6 /usr/bin/designer6 &&
ln -sf /usr/lib/share/icons/hicolor/128x128/apps/designer.png /usr/share/pixmaps/designer.png &&
ln -sf /usr/lib/share/applications/linguist.desktop /usr/share/applications/linguist.desktop &&
ln -sf /usr/lib/bin/linguist6 /usr/bin/linguist6 &&
ln -sf /usr/lib/share/icons/hicolor/128x128/apps/linguist.png /usr/share/pixmaps/linguist.png &&
ln -sf /usr/lib/share/applications/qdbusviewer.desktop /usr/share/applications/qdbusviewer.desktop &&
ln -sf /usr/lib/bin/qdbusviewer6 /usr/bin/qdbusviewer6 &&
ln -sf /usr/lib/share/icons/hicolor/128x128/apps/qdbusviewer.png /usr/share/pixmaps/qdbusviewer.png
