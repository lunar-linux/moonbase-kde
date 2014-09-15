
  patch_it $SOURCE2 1 &&

  OPTS+=" -DRAPTOR_INCLUDE_DIR=/usr/include/raptor2" &&

  if in_depends $MODULE sun-jdk; then
    . /etc/profile.d/sun-jdk.rc
  else
    if in_depends $MODULE sun-jre; then
      . /etc/profile.d/sun-jre.rc
    fi
  fi  &&

  source /etc/profile.d/qt4.rc  &&

  default_cmake_build
