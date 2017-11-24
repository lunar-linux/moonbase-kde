
  . /etc/profile.d/qt4.rc &&

#If not specify Release it thinks it is using debug and make will fail
  OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_DOC=0" &&

  default_cmake_build &&

  # Desktop menu entry
  cat > ${MODULE}.desktop << EOF  &&
[Desktop Entry]
Type=Application
Name=Tulip
Comment=Graph visualization software
Exec=$QTDIR/bin/tulip
Icon=/usr/share/tulip/bitmaps/logo.bmp
Categories=Qt;KDE;Science;
EOF

  install -D -m644 ${MODULE}.desktop /usr/share/applications/${MODULE}.desktop
