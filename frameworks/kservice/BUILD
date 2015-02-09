
  source /etc/profile.d/qt5.rc &&

# Some of the internationalization is borked
  rm -rf po/nl po/pt_BR po/sv po/uk &&
  sedit "111,127d" docs/desktoptojson/man-desktoptojson.8.docbook &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DBUILD_TESTING=0" &&

  default_cmake_build
