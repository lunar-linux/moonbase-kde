
  . /etc/profile.d/qt5.rc   &&
  . /etc/profile.d/kde4.rc  &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DQT_INCLUDES=/usr/include/qt5 -DBUILD_TESTING=0  \
          -DQt5_LIBRARIES=/usr/lib/qt5/libQt5Gui.so -DQT_LIBRARIES=/usr/lib/qt5/libQt5Gui.so" &&

  default_cmake_build
