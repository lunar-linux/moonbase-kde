(

  sedit 's/vnd.scribus.desktop/scribus.desktop/' CMakeLists.txt &&
  sedit 's/## PL We may not need this anymore/INSTALL(FILES scribus.desktop DESTINATION ${DESKTOPDIR} )/' CMakeLists.txt &&

  source /etc/profile.d/qt4.rc &&

  default_cmake_build &&

  install -Dm0644 ${SOURCE_DIRECTORY}/resources/icons/AppIcon.png /usr/share/icons/hicolor/32x32/apps/scribus.png

) > $C_FIFO 2>&1
