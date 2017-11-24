
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DOXYGEN_FONT_INSTALL_DIR=/usr/share/fonts/oxygen-fonts" &&

  default_cmake_config &&

  make &&
  prepare_install &&
  mkdir -p /usr/share/fonts/oxygen-fonts &&
  mkdir -p /usr/lib/cmake/OxygenFont &&
  install -m644 *.ttf /usr/share/fonts/oxygen-fonts/ &&
  install OxygenFontConfig* /usr/lib/cmake/OxygenFont/ &&
  gather_docs &&
  cp ../*GPL* ../*OFL* /usr/share/doc/oxygen-fonts &&

  message "Running fc-cache please be patient" &&
  fc-cache -f
