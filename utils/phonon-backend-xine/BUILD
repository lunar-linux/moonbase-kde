export CFLAGS="$CFLAGS -fPIC" &&

if module_installed qt4; then
  source /etc/profile.d/qt4.rc &&
  source /etc/profile.d/kde4.rc
fi &&

if module_installed qt5; then
  source /etc/profile.d/qt5.rc
fi &&

default_cmake_build
