
  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

# The current version of ruby-2.2.2 installs headers into ruby-2.2.0
  if in_depends $MODULE ruby ; then
    OPTS+=" -DRUBY_INCLUDE_PATH=/usr/include/ruby-2.2.0"
  fi &&

  default_cmake_build
