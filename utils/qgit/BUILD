
  . /etc/profile.d/qt5.rc  &&

  /usr/lib/qt5/bin/qmake qgit.pro &&
  make  &&
  prepare_install  &&
  install -m 755 -s bin/qgit /usr/bin  &&
  mkdir -p /usr/share/icons/  &&
  install -m 644 src/resources/qgit.ico /usr/share/icons/  &&

    # Desktop menu entry
  cat > ${MODULE}.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=qgit
Comment=Qt interface for git
Exec=/usr/bin/qgit
Icon=/usr/share/icons/qgit.ico
Categories=Qt;KDE;Development;
EOF

  install -D -m644 ${MODULE}.desktop /usr/share/applications/${MODULE}.desktop
