
  . /etc/profile.d/qt4.rc  &&

# To deal with current version of openssl
sedit "5406i #ifndef OPENSSL_NO_SSL3_METHOD" plugins/qca-ossl/qca-ossl.cpp &&
sedit "5410i #endif" plugins/qca-ossl/qca-ossl.cpp &&

  OPTS+=" -DQT4_BUILD=1 \
          -DQCA_SUFFIX=qt4 \
          -DBUILD_TESTS=0  \
          -DQCA_LIBRARY_INSTALL_DIR=/usr/lib \
          -DQCA_FEATURE_INSTALL_DIR=/usr/share/qt4/mkspecs/features/" &&
  default_cmake_build

  mv $SOURCE_DIRECTORY/$MODULE-oosb $SOURCE_DIRECTORY/$MODULE.qt4-oosb &&

  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DQT4_BUILD=0 -DQCA_SUFFIX=qt5 -DBUILD_TESTS=0 -DQCA_INSTALL_IN_QT_PREFIX=1" &&

  default_cmake_build
