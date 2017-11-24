
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

# Disabling these, they conflict with kate from applications.
# This module exists primarily for rkward and its dependency on katepart
  OPTS+=" -DBUILD_kate=0 -DBUILD_kwrite=0 -DBUILD_addons=0 -DBUILD_doc=0 -DBUILD_tests=0" &&

  default_cmake_build
