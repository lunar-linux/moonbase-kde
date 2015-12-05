
  patch_it $SOURCE2 1 &&

  . /etc/profile.d/qt4.rc  &&
  OPTS+=" -DBUILD_WITH_QT4=1" &&
  default_cmake_build &&

  devoke_installwatch &&

  mv $SOURCE_DIRECTORY/$MODULE-oosb $SOURCE_DIRECTORY/$MODULE.qt4-oosb &&

  . /etc/profile.d/qt5.rc &&
  OPTS+=" -DBUILD_WITH_QT4=0" &&
  default_cmake_build
