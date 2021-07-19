# This is temporary till https://bugs.kde.org/show_bug.cgi?id=439541 is resolved.
  rm -rf po/de &&

  . /etc/profile.d/qt5.rc   &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DFETCH_TRANSLATIONS=OFF" &&

  default_cmake_build
