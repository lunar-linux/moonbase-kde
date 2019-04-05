
  . /etc/profile.d/qt5.rc   &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  sedit 's:buffio:tidybuffio:' plugins/validators/tidy_validator.cpp &&

  default_cmake_build
