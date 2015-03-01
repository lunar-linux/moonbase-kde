
  default_make &&

# Still need the bin dir here for those modules like google-gadgets-for-linux that
# want to use this path.
  mkdir -p /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin &&
  ln -sf /usr/bin/moc /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/moc &&
  ln -sf /usr/bin/qmake /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/qmake &&
  ln -sf /usr/bin/uic /usr/share/qt4/Trolltech/Qt-`lvu version qt4`/bin/uic &&
 
# It wants to point moc_location and uic_location to ${prefix}/src/qt-everywhere-opensource-src-4.8.4/bin
# and after much fiddling cannot get it to point them to /usr/bin. So lets just sedit these rascals.
  for i in `ls /usr/lib/$MODULE/pkgconfig/Q*.pc` ; do sed -i "s:/usr/src/qt-everywhere-opensource-src-$VERSION:/usr:" $i ; done &&
  if [ -f /usr/lib/$MODULE/pkgconfig/phonon.pc ]; then
  sed -i "s:/usr/src/qt-everywhere-opensource-src-$VERSION/:/usr:" /usr/lib/$MODULE/pkgconfig/phonon.pc
  fi &&
# Some more cleanup
  sedit "s:-L/usr/src/qt-everywhere-opensource-src-$VERSION/lib::" /usr/lib/$MODULE/pkgconfig/Qt{Designer,DesignerComponents,UiTools}.pc &&
# Like for moc and uic, the same needs doing for the *.prl files.
  find /usr/lib/qt4 -type f -name '*.prl' \
      -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

  if [[ "$MAKE_EXAMPLE_DEMOS" == "y" ]] ; then
  cat > ${MODULE}-designer.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Qt4 Designer
Comment=Design GUIs for Qt4 applications
Exec=${MODULE_PREFIX}/bin/designer
Icon=${MODULE_PREFIX}/share/doc/qt4/widgets/icons/images/designer.png
Categories=Qt;Development;
Terminal=false
EOF
  install -D -m644 ${MODULE}-designer.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-designer.desktop 

  cat > ${MODULE}-assistant.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Qt4 Assistant
Comment=Shows Qt4 documentation and examples
Exec=${MODULE_PREFIX}/bin/assistant
Icon=${MODULE_PREFIX}/share/qt4/src/images/assistant-assistant.png
Categories=Qt;Development;Documentation;
Terminal=false
EOF
  install -D -m644 ${MODULE}-assistant.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-assistant.desktop

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
  install -D -m644 ${MODULE}-qtdemo.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-qtdemo.desktop
fi &&

  cat > ${MODULE}-qtconfig.desktop << EOF  &&
[Desktop Entry]
Name=Qt4 Config 
Comment=Configure Qt4 behavior, styles, fonts
Exec=${MODULE_PREFIX}/bin/qtconfig
Icon=${MODULE_PREFIX}/share/$MODULE/src/images/qt-logo.png
Terminal=false
Type=Application
Categories=Qt;Settings;
EOF
  install -D -m644 ${MODULE}-qtconfig.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-qtconfig.desktop &&

  cat > ${MODULE}-linguist.desktop << EOF  &&
[Desktop Entry]
Name=Qt4 Linquist
Comment=Add translations to Qt4 applications
Exec=${MODULE_PREFIX}/bin/linguist
Icon=${MODULE_PREFIX}/share/$MODULE/src/images/linguist-linguist.png
Terminal=false
Type=Application
Categories=Qt;Settings;
EOF
  install -D -m644 ${MODULE}-linguist.desktop ${MODULE_PREFIX}/share/applications/${MODULE}-linguist.desktop &&

  echo "export QTDIR=\"${MODULE_PREFIX}\"" > $SOURCE_DIRECTORY/$MODULE.rc &&
  echo export QT_PLUGIN_PATH=\"'${QTDIR}'/lib/${MODULE}/plugins\" >> $SOURCE_DIRECTORY/$MODULE.rc &&
  echo export XDG_DATA_DIRS=\"'${XDG_DATA_DIRS:-/usr/share}':/usr/share/$MODULE\" >> $SOURCE_DIRECTORY/$MODULE.rc &&
  echo export PKG_CONFIG_PATH=\"'${QTDIR}'/lib/${MODULE}/pkgconfig:'${PKG_CONFIG_PATH}'\" >> $SOURCE_DIRECTORY/$MODULE.rc &&

  install -m644 $SOURCE_DIRECTORY/$MODULE.rc /etc/profile.d/
