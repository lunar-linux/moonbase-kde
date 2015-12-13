
  . /etc/profile.d/qt4.rc  &&

  OPTS+=" -DQT4_BUILD=1 -DQCA_SUFFIX=qt4 -DBUILD_TESTS=0" &&
  default_cmake_build

  mv $SOURCE_DIRECTORY/$MODULE-oosb $SOURCE_DIRECTORY/$MODULE.qt4-oosb &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DQT4_BUILD=0 -DQCA_SUFFIX=qt5 -DBUILD_TESTS=0 -DQCA_INSTALL_IN_QT_PREFIX=1" &&

  default_cmake_build
