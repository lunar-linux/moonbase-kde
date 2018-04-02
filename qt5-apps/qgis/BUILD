  . /etc/profile.d/qt5.rc &&

# Remove mime types already defined by freedesktop.org
  sed -e '/type="image\/tiff"/,/<\/mime-type>/d' \
      -e '/type="image\/jpeg"/,/<\/mime-type>/d' \
      -e '/type="image\/jp2"/,/<\/mime-type>/d' \
      -e '/type="application\/x-adobe-mif"/,/<\/mime-type>/d' \
      -i debian/qgis.xml &&

  OPTS+=" -DQSCINTILLA_INCLUDE_DIR=/usr/include/qt5/ \
          -DQSCINTILLA_LIBRARY=/usr/lib/qt5/libqscintilla2_qt5.so \
          -DQWT_INCLUDE_DIR=/usr/include/qwt/ \
          -DQWT_LIBRARY=/usr/lib/qwt-6/libqwt.so \
          -DQCA_INCLUDE_DIR=/usr/include/Qca-qt5/QtCrypto/ \
          -DQCA_LIBRARY=/usr/lib/libqca-qt5.so" &&

  LDFLAGS+=" -Wl,-rpath,/usr/lib/qwt-6/" &&
  default_cmake_build &&

  cat > ${MODULE}.desktop << EOF  &&
[Desktop Entry]
Name=QGIS Desktop
Comment=Qt based Geographic Information System
Exec=/usr/bin/qgis
Icon=/usr/share/qgis/images/icons/qgis-icon-16x16.png
Terminal=false
Type=Application
Categories=Qt;Education;Science;
EOF
  install -D -m644 ${MODULE}.desktop /usr/share/applications/${MODULE}.desktop &&

  cat > qbrowser.desktop << EOF  &&
[Desktop Entry]
Name=QGIS Browser
Comment=QGIS Geographic Information System Browser
Exec=/usr/bin/qbrowser %F
Icon=/usr/share/qgis/images/icons/qgis-icon-macos.png
Terminal=false
Type=Application
Categories=Qt;Education;Science;
EOF
  install -D -m644 qbrowser.desktop /usr/share/applications/qbrowser.desktop

