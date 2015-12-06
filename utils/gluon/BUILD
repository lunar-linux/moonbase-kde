
  sed -i "26i #include <unistd.h>" input/linux/detectlinux.cpp input/linux/inputthread.cpp &&

  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&

  OPTS+=" -DBUILD_PHYSICS_COMPONENTS=ON -DBUILD_PHYSICS_ASSETS=ON -DBUILD_GLUON_PLAYER=ON" &&

  default_cmake_build
