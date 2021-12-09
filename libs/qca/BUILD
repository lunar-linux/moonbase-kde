  . /etc/profile.d/qt5.rc &&


  OPTS+=" -DBUILD_TESTS=0 \
          -DQT6=OFF \
          -DQCA_INSTALL_IN_QT_PREFIX=ON \
          -DQCA_FEATURE_INSTALL_DIR=/usr/lib/qt5/mkspec/features \
          -DQCA_PLUGINS_INSTALL_DIR=/usr/lib/qt5/plugins" &&

  default_cmake_build
