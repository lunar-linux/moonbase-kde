
  . /etc/profile.d/qt5.rc &&

  OPTS+="  -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  sed -i 's/isnan/std::isnan/g' `grep "isnan" -rl` &&
  sed -i 's/<math\.h>/<cmath>/g' `grep "math.h" -rl` &&

  default_cmake_build
  
