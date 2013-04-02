(

  source /etc/profile.d/qt4.rc &&

# Another cmake base build type that is case sensitive. Using all
# upper case confuses it into thinking parts built as debug with
# others as Release.
  OPTS+=" -DCMAKE_BUILD_TYPE=Release" &&

  sedit "s:ADD_SUBDIRECTORY(doc)::" CMakeLists.txt &&


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

) > $C_FIFO 2>&1
