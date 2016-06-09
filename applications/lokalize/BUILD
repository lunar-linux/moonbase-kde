
  . /etc/profile.d/qt5.rc   &&

  LDFLAGS+=" -lhunspell" &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1  \
          -DHUNSPELL_INCLUDE_DIR=/usr/include/hunspell \
          -DHUNSPELL_LIBRARIES=/usr/lib" &&

  default_cmake_build
