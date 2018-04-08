
  CXXFLAGS+=" -std=c++11 -fPIC" &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr" &&

  cd $MODULE &&

  cmake $OPTS . &&

  default_make
