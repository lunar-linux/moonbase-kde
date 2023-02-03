source /etc/profile.d/qt5.rc &&

if in_depends kio-fuse; then
  OPTS+=" -DKIOFuse_PATH=/usr/lib/kio-fuse"
fi &&

  OPTS+="  -DCMAKE_INSTALL_LIBEXECDIR=lib -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  default_cmake_build
