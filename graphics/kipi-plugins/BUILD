
  OPTS+=" -DBUILD_simpletreemodel=0 -DBUILD_tests=0 -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr" 

  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&

  cd extra/kipi-plugins/ &&

  mkdir build &&
  cd build &&
  cmake ../ $OPTS &&
  default_make
