
# Do the qt4 first
#  . /etc/profile.d/qt4.rc &&
#  OPTS+=" -DPHONON_BUILD_PHONON4QT5=OFF" &&
#  default_cmake_build &&

# Now for the qt5 part if installed
  . /etc/profile.d/qt5.rc &&
  if module_installed qt5 ; then
    OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON" &&
    default_cmake_build
  fi
