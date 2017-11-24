
  if in_depends $MODULE speech-dispatcher ;  then
    sedit "s:libspeechd.h:speech-dispatcher/libspeechd.h:" kaccessibleapp.cpp &&
    OPTS+=" -DSPEECHD_INCLUDE_DIR=/usr/include/speech-dispatcher"
  fi &&

  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  default_cmake_build
