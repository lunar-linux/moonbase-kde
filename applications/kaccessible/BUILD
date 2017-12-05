
  source /etc/profile.d/qt5.rc   &&

  if in_depends $MODULE speech-dispatcher ;  then
    sedit "s:libspeechd.h:speech-dispatcher/libspeechd.h:" kaccessibleapp.cpp &&
    OPTS+=" -DSPEECHD_INCLUDE_DIR=/usr/include/speech-dispatcher"
  fi &&

  default_cmake_build
