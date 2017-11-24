OPTS+=" -DENABLE_EXAMPLES=OFF -DENABLE_TESTS=OFF"
if in_depends $MODULE qt4; then
  . /etc/profile.d/qt4.rc &&
  # make a backup copy of OPTS
  OPTS_BAK=OPTS
  OPTS+=" -DDESIRED_QT_VERSION=4" &&
  default_cmake_build &&
  # restore the backup copy of OPTS
  OPTS=OPTS_BAK
fi &&

. /etc/profile.d/qt5.rc &&
OPTS+=" -DDESIRED_QT_VERSION=5" &&
default_cmake_build
