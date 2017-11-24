
  default_cmake_build &&

  cat > ${MODULE}.desktop << EOF  &&
[Desktop Entry]
Name=QGIS Desktop
Comment=Qt based Geographic Information System
Exec=/usr/bin/qgis
Icon=/usr/share/qgis/images/icons/qgis-icon.png
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
Icon=/usr/share/qgis/images/icons/qgis-icon.png
Terminal=false
Type=Application
Categories=Qt;Education;Science;
EOF
  install -D -m644 qbrowser.desktop /usr/share/applications/qbrowser.desktop

