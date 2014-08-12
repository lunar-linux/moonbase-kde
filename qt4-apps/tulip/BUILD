
#  patch_it $SOURCE2 2 &&

  source /etc/profile.d/qt4.rc &&

  sedit "s:FTGL/FTGL.h:FTGL/ftgl.h:g" FindFTGL.cmake &&
# Recent changes to binutils improperly requires binutils config.h to 
# be present for external source code when using bfd.h. This sedit just
# deletes cmake looking for bfd.h.
#  sedit "12d" software/crash_handling/CMakeLists.txt &&

# Another cmake base build type that is case sensitive. Using all
# upper case confuses it into thinking parts built as debug with
# others as Release.
  OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_DOC=0" &&

#  sedit "s:ADD_SUBDIRECTORY(doc)::" CMakeLists.txt &&

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
