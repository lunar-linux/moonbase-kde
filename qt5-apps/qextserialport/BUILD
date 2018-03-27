  mkdir build && cd build &&
  /usr/lib/qt5/bin/qmake .. &&

  default_make &&

  # Fix wrong path in prl files
  sed -i '/^QMAKE_PRL_BUILD_DIR/d' "/usr/lib/qt5/"*.prl
