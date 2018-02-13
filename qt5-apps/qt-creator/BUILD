source /etc/profile.d/qt5.rc &&

QT_CREATOR_BLD="$SOURCE_DIRECTORY/creator-build" &&

mkdir $QT_CREATOR_BLD &&
cd $QT_CREATOR_BLD &&

/usr/lib/qt5/bin/qmake \
LLVM_INSTALL_DIR=/usr QMAKE_CFLAGS_ISYSTEM=-I CONFIG+=journald -r $SOURCE_DIRECTORY/qtcreator.pro &&

make &&
if [[ $MAKE_DOCS == "y" ]] ; then
  make docs -j1
fi &&
prepare_install &&

make INSTALL_ROOT=$MODULE_PREFIX/ install &&

# Desktop menu entry
cat > $MODULE.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Qt Creator
Comment=Qt based Development Tool
Exec=$QTDIR/bin/qtcreator
Icon=/usr/share/icons/hicolor/512x512/apps/QtProject-qtcreator.png
Categories=Application;Qt;KDE;Development;
EOF

install -D -m644 $MODULE.desktop /usr/share/applications/$MODULE.desktop &&

# workaround for a runtime bug
mv /usr/bin/qtcreator /usr/bin/qtcreator-bin
echo "#!/bin/sh" > /usr/bin/qtcreator
echo "QT_LOGGING_TO_CONSOLE=1 qtcreator-bin \$@" >> /usr/bin/qtcreator
chmod +x /usr/bin/qtcreator
