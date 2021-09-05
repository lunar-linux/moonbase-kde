. /etc/profile.d/qt5.rc &&

if in_depends $MODULE qwtpolar; then
  OPTS+=" -DQWT_INCLUDE_DIR=/usr/include/qwt \
          -DQWT_LIBRARY=/usr/lib/qwt-6/libqwt.so"
fi &&

OPTS+=" -DQSCINTILLA_INCLUDE_DIR=/usr/include/qt5/ \
        -DQSCINTILLA_LIBRARY=/usr/lib/qt5/libqscintilla2_qt5.so \
        -DQCA_INCLUDE_DIR=/usr/include/qt5/Qca-qt5/QtCrypto \
        -DQCA_LIBRARY=/usr/lib/qt5/libqca-qt5.so \
        -DENABLE_TESTS=OFF \
        -DWITH_QSPATIALITE=ON \
        -DWITH_CUSTOM_WIDGETS=ON \
        -DWITH_APIDOC=OFF \
        -DWITH_3D=ON"


default_cmake_build
