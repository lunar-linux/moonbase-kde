
# Do the qt4 first
  OPTS+=" -DPHONON_BUILD_PHONON4QT5=OFF" &&
  default_cmake_build &&

# Now for the qt5 part if installed
  if module_installed qt5 ; then
    OPTS+=" -DPHONON_BUILD_PHONON4QT5=ON" &&
    default_cmake_build
  fi
