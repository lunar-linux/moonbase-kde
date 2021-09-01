
  . /etc/profile.d/qt5.rc &&

  /usr/lib/qt5/bin/qmake PREFIX=/usr/share &&

  default_build &&

cat > ${MODULE}.desktop << EOF &&
[Desktop Entry]
Type=Application
Exec=/usr/bin/vym
Icon=/usr/share/vym/icons/vym.png
MimeType=application/x-vym;
Categories=Qt;KDE;Education;
Name=VYM - View Your Mind
EOF

install -D -m644 ${MODULE}.desktop /usr/share/applications/${MODULE}.desktop
