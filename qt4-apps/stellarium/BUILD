
  source /etc/profile.d/qt4.rc   &&

# they insist on using the always outdated qt4 version of phonon
# which conflicts with phonon
  if [[ "$(get_other_module_config qt4 MAKE_PHONON)" = "n" ]]; then 
    OPTS+=" -DENABLE_SOUND=OFF"
  fi &&

  default_cmake_build 
