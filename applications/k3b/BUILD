  . /etc/profile.d/qt5.rc &&

  sed -i -e 's/^cmake_minimum/#cmake_minimum/' CMakeLists.txt && 

  OPTS+=" -DK3B_ENABLE_PERMISSION_HELPER=ON -DSYSCONF_INSTALL_DIR=/etc/kde" &&

  default_cmake_build
