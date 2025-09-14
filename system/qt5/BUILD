# This needs to happen here since CFLAGS/CXXFLAGS/LDFLAGS is only loaded during BUILD
if in_depends $MODULE libressl; then
  patch_it $SCRIPT_DIRECTORY/libressl-compat.patch 1 &&
  CFLAGS+=" -DOPENSSL_NO_PSK -DOPENSSL_NO_NEXTPROTONEG" &&
  CXXFLAGS+=" -DOPENSSL_NO_PSK -DOPENSSL_NO_NEXTPROTONEG -Wno-deprecated-declarations -Wno-class-memaccess -Wno-packed-not-aligned -Wno-deprecated-declarations -fno-delete-null-pointer-checks"
fi &&

if [[ $LICENSE_TYPE == "y" ]]; then
  LICENSE_TYPE="-opensource"
else
  LICENSE_TYPE="-commercial"
fi &&

# No SSE2 for i686
if [[ 'arch' == "i686" ]]; then
  SSE2="-no-sse2"
fi &&

# Making accessibility a hard option, disabling this will break QStyle and may break other internal parts of Qt and
# create a source incompatible version which is unsupported. Why bother making it a switch if that is the case.
# no-gtkstyle, grabs qt-5 headers via cairo when built with qt5.
# Just a note about rpath vs linux as used here by qt5; don't use -rpath, lets stay with -no-rpath.
# See https://bugreports.qt.io/browse/QTBUG-33948.

OPTS+=" -gui \
        -gtk \
        -no-icu \
        -xcb \
        -strip \
        -release \
        -no-rpath \
        -system-pcre \
        -system-zlib \
        -system-libpng \
        -system-libjpeg \
        -skip qtwebengine \
        -nomake examples \
        -accessibility \
        -reduce-relocations \
        -dbus-linked \
        -confirm-license $LICENSE_TYPE -v \
        $SSE2" &&

# broken with assimp 5.1.3
OPTS+=" --quick3d-assimp=qt" &&

if [[ "$USE_JOURNALD" == "y" && $(module_installed systemd) ]]; then
  OPTS+=" -journald"
 else
  OPTS+=" -no-journald"
fi


mkdir build-qt &&
cd build-qt &&
../configure -sysconfdir "/etc/xdg" \
            -prefix "${MODULE_PREFIX}" \
            -confirm-license "${LICENSE_TYPE}" \
            -libdir "${MODULE_PREFIX}/lib/$MODULE" \
            -datadir "${MODULE_PREFIX}/share/$MODULE" \
            -bindir "${MODULE_PREFIX}/lib/$MODULE/bin" \
            -archdatadir "${MODULE_PREFIX}/lib/$MODULE" \
            -docdir "${MODULE_PREFIX}/share/doc/$MODULE" \
            -headerdir "${MODULE_PREFIX}/include/$MODULE" \
            -plugindir "${MODULE_PREFIX}/lib/$MODULE/plugins" \
            -examplesdir "${MODULE_PREFIX}/share/doc/$MODULE"/examples \
            -translationdir "${MODULE_PREFIX}/share/$MODULE"/translations \
            $OPTS &&

# system rapidjson compiles fine, the same version provided by qt5 does not, so delete the offending line
sedit '319d' ../qtlocation/src/3rdparty/mapbox-gl-native/deps/rapidjson/1.1.0/include/rapidjson/document.h &&

make &&
prepare_install &&

# If this directory exists the install fails
rm -fR /usr/lib/pkgconfig/qtwebkit &&

make install &&

install -v -Dm644 ../qttools/src/assistant/assistant/images/assistant-128.png /usr/share/pixmaps/assistant-qt5.png &&
install -v -Dm644 ../qttools/src/designer/src/designer/images/designer.png /usr/share/pixmaps/designer-qt5.png &&
install -v -Dm644 ../qttools/src/linguist/linguist/images/icons/linguist-128-32.png /usr/share/pixmaps/linguist-qt5.png &&
install -v -Dm644 ../qttools/src/qdbus/qdbusviewer/images/qdbusviewer-128.png /usr/share/pixmaps/qdbusviewer-qt5.png &&

# It wants to point moc_location and uic_location to ${prefix}/src/qt-everywhere-opensource-src-5.3.1/bin
# and after much fiddling cannot get it to point them to /usr/bin. So lets just sedit these rascals.
for i in `ls /usr/lib/$MODULE/pkgconfig/Qt5*.pc`; do sed -i "s:/usr/src/$SOURCE_DIRECTORY:/usr:" $i; done &&
for i in `ls /usr/lib/$MODULE/pkgconfig/Qt5*.pc`; do sed -i "s:-L$SOURCE_DIRECTORY:/usr:" $i; done &&

# Like for moc and uic, the same needs doing for the *.prl files.
find /usr/lib/$MODULE -type f -name '*Qt5*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&
find /usr/lib/$MODULE -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

# Remove references to the build directory from installed files
sedit "s:$PWD/qtbase:/usr/lib/qt5:g" /usr/lib/qt5/mkspecs/modules/qt_lib_bootstrap_private.pri &&

cat > ${MODULE}-designer.desktop << EOF &&
[Desktop Entry]
Type=Application
Name=Qt5 Designer
Comment=Design GUIs for Qt5 applications
Exec=${MODULE_PREFIX}/lib/$MODULE/bin/designer
Icon=${MODULE_PREFIX}/share/pixmaps/designer-qt5.png
Categories=Qt;Development;
Terminal=false
EOF

install -D -m644 ${MODULE}-designer.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-designer.desktop &&

cat > ${MODULE}-assistant.desktop << EOF &&
[Desktop Entry]
Type=Application
Name=Qt5 Assistant
Comment=Shows Qt5 documentation and examples
Exec=${MODULE_PREFIX}/lib/$MODULE/bin/assistant
Icon=${MODULE_PREFIX}/share/pixmaps/assistant-qt5.png
Categories=Qt;Development;Documentation;
Terminal=false
EOF

install -D -m644 ${MODULE}-assistant.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-assistant.desktop &&

cat > ${MODULE}-qtconfig.desktop << EOF &&
[Desktop Entry]
Name=Qt5 QDbusViewer
GenericName=D-Bus Debugger
Comment=Debug D-Bus applications
Exec=${MODULE_PREFIX}/lib/$MODULE/bin/qdbusviewer
Icon=${MODULE_PREFIX}/share/pixmaps/qdbusviewer-qt5.png
Terminal=false
Encoding=UTF-8
Type=Application
Categories=Qt;Development;Debugger;
EOF

install -D -m644 ${MODULE}-qtconfig.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-qtconfig.desktop &&

cat > ${MODULE}-linguist.desktop << EOF &&
[Desktop Entry]
Name=Qt5 Linquist
Comment=Add translations to Qt5 applications
Exec=${MODULE_PREFIX}/lib/$MODULE/bin/linguist
Icon=${MODULE_PREFIX}/share/pixmaps/linguist-qt5.png
Terminal=false
Type=Application
Categories=Qt;Settings;
EOF

install -D -m644 ${MODULE}-linguist.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-linguist.desktop &&

cat > $MODULE.rc << EOF &&
export Qt5_DIR="${MODULE_PREFIX}"
export QT5_PLUGIN_PATH="\${Qt5_DIR}/lib/${MODULE}/plugins"
export XDG_DATA_DIRS="\${XDG_DATA_DIRS:-/usr/share}:/usr/share/$MODULE"
export PKG_CONFIG_PATH="\${Qt5_DIR}/lib/${MODULE}/pkgconfig:\${PKG_CONFIG_PATH}"
export PATH="\${Qt5_DIR}/lib/${MODULE}/bin:\${PATH}"
export CMAKE_PREFIX_PATH="\${Qt5_DIR}/lib/qt5/cmake:\${CMAKE_PREFIX_PATH}"
export RCC="\${Qt5_DIR}/lib/qt5/bin/rcc"
export MOC="\${Qt5_DIR}/lib/qt5/bin/moc"
export UIC="\${Qt5_DIR}/lib/qt5/bin/uic"
EOF

install -m644 ${MODULE}.rc /etc/profile.d/${MODULE}.rc &&

# Avoid the Qt5WebKit files
for f in /usr/lib/qt5/pkgconfig/*; do
  if [[ $f != *"Qt5WebKit"* ]]; then
     mv -f $f /usr/lib/pkgconfig/
  fi
done &&

ln -sf /usr/lib/pkgconfig/Qt*.pc /usr/lib/qt5/pkgconfig/ &&

for file in moc uic rcc qmake lconvert lrelease lupdate; do
  ln -sfrvn /usr/lib/qt5/bin/$file /usr/bin/$file-qt5
done &&

# for some reason data files are installed without read permissions
chmod +rX /usr/share/qt5 -R
