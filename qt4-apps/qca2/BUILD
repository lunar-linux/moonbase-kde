
  . /etc/profile.d/qt4.rc  &&

  OPTS+=" -DQT4_BUILD=1 -DQCA_SUFFIX=qt4" &&
  default_cmake_build

  mv $SOURCE_DIRECTORY/$MODULE-oosb $SOURCE_DIRECTORY/$MODULE.qt4-oosb &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DQT4_BUILD=0 -DQCA_SUFFIX=qt5" &&

  default_cmake_build
