
  . /etc/profile.d/qt4.rc &&

  cd $MODULE-$VERSION &&
  mkdir build-lunar &&
  cd build-lunar &&
  cmake -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX -DCMAKE_BUILD_TYPE=RELEASE -DSYSCONF_INSTALL_DIR:PATH=/etc -Wno-dev $OPTS .. &&
  default_make

