if module_installed qt4; then
  . /etc/profile.d/qt4.rc &&
  default_cmake_build
fi &&

if module_installed qt5; then
  . /etc/profile.d/qt5.rc &&
  OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON" &&
  default_cmake_build
fi
