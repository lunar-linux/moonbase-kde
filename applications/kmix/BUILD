
  . /etc/profile.d/qt4.rc  &&
  . /etc/profile.d/kde4.rc &&

  default_cmake_build &&

  devoke_installwatch &&

  . /etc/profile.d/qt5.rc  &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DKMIX_KF5_BUILD=1" &&

  default_cmake_build
