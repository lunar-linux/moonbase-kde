# Temporary. Make failes if no jit. Will revisit on next bump. Found by keios.
OPTS+=" -scripttools -no-declarative-debug -release -optimized-qmake" &&

# icu4c 61.1 requires c++11 and thus breaks qt4 and the packaged webkit
OPTS+=" -no-icu -no-webkit" &&

# Build with gcc 6.2+
CXXFLAGS+=" -std=gnu++98 -Wno-deprecated" &&

./configure -confirm-license -opensource        \
            -prefix /usr                        \
            -bindir /usr/bin                    \
            -libdir /usr/lib/$MODULE            \
            -docdir /usr/share/doc/$MODULE      \
            -headerdir /usr/include/$MODULE     \
            -plugindir /usr/lib/$MODULE/plugins \
            -importdir /usr/lib/$MODULE/imports \
            -datadir /usr/share/$MODULE         \
            -sysconfdir /etc/xdg                \
            -demosdir /usr/share/doc/$MODULE/demos \
            -examplesdir /usr/share/doc/$MODULE/examples \
            -translationdir /usr/share/$MODULE/translations \
            $OPTS

default_make &&

# Still need the bin dir here for those modules like google-gadgets-for-linux that
# want to use this path.
mkdir -p /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin &&
ln -sf /usr/bin/moc   /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/moc &&
ln -sf /usr/bin/qmake /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/qmake &&
ln -sf /usr/bin/uic   /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/uic &&

# It wants to point moc_location and uic_location to ${prefix}/src/qt-everywhere-opensource-src-4.8.4/bin
# and after much fiddling cannot get it to point them to /usr/bin. So lets just sedit these rascals.
for i in `ls /usr/lib/pkgconfig/Q*.pc`; do
  sed -i "s:/usr/src/qt-everywhere-opensource-src-$VERSION:/usr:" $i
done &&
if [ -f /usr/lib/pkgconfig/phonon.pc ]; then
  sed -i "s:/usr/src/qt-everywhere-opensource-src-$VERSION/:/usr:" /usr/lib/pkgconfig/phonon.pc
fi &&

# Some more cleanup
sedit "s:-L/usr/src/qt-everywhere-opensource-src-$VERSION/lib::" /usr/lib/$MODULE/pkgconfig/Qt{Designer,DesignerComponents,UiTools}.pc &&

# Like for moc and uic, the same needs doing for the *.prl files.
find /usr/lib/qt4 -type f -name '*.prl' \
     -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

if [[ "$MAKE_DEMOS" == "y" ]] ; then
  cat > ${MODULE}-designer.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Qt4 Designer
Comment=Design GUIs for Qt4 applications
Exec=/usr/bin/designer
Icon=/usr/share/doc/qt4/widgets/icons/images/designer.png
Categories=Qt;Development;
Terminal=false
EOF
  install -D -m644 ${MODULE}-designer.desktop /usr/share/applications/${MODULE}-designer.desktop 

  cat > ${MODULE}-assistant.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Qt4 Assistant
Comment=Shows Qt4 documentation and examples
Exec=/usr/bin/assistant
Icon=/usr/share/qt4/src/images/assistant-assistant.png
Categories=Qt;Development;Documentation;
Terminal=false
EOF
  install -D -m644 ${MODULE}-assistant.desktop /usr/share/applications/${MODULE}-assistant.desktop

  cat > ${MODULE}-qtdemo.desktop << EOF  &&
[Desktop Entry]
Name=Qt4 Demo
Comment=Show Qt4 demos and programming examples
Exec=${MODULE_PREFIX}/bin/qtdemo
Icon=${MODULE_PREFIX}/share/$MODULE/src/images/qt-logo.png
Terminal=false
Type=Application
Categories=Qt;Development;
EOF
  install -D -m644 ${MODULE}-qtdemo.desktop /usr/share/applications/${MODULE}-qtdemo.desktop
fi &&

cat > ${MODULE}-qtconfig.desktop << EOF  &&
[Desktop Entry]
Name=Qt4 Config
Comment=Configure Qt4 behavior, styles, fonts
Exec=/usr/bin/qtconfig
Icon=/usr/share/$MODULE/src/images/qt-logo.png
Terminal=false
Type=Application
Categories=Qt;Settings;
EOF
install -D -m644 ${MODULE}-qtconfig.desktop /usr/share/applications/${MODULE}-qtconfig.desktop &&

cat > ${MODULE}-linguist.desktop << EOF  &&
[Desktop Entry]
Name=Qt4 Linquist
Comment=Add translations to Qt4 applications
Exec=/usr/bin/linguist
Icon=/usr/share/$MODULE/src/images/linguist-linguist.png
Terminal=false
Type=Application
Categories=Qt;Settings;
EOF
install -D -m644 ${MODULE}-linguist.desktop /usr/share/applications/${MODULE}-linguist.desktop &&

echo "export QTDIR=\"/usr\"" > $SOURCE_DIRECTORY/$MODULE.rc &&
echo export QT_PLUGIN_PATH=\"'${QTDIR}'/lib/${MODULE}/plugins\" >> $SOURCE_DIRECTORY/$MODULE.rc &&
echo export XDG_DATA_DIRS=\"'${XDG_DATA_DIRS:-/usr/share}':/usr/share/$MODULE\" >> $SOURCE_DIRECTORY/$MODULE.rc &&

install -m644 $SOURCE_DIRECTORY/$MODULE.rc /etc/profile.d/ &&

mv -f /usr/lib/qt4/pkgconfig/* /usr/lib/pkgconfig/ &&
rmdir /usr/lib/qt4/pkgconfig
