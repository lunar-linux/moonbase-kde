. /etc/profile.d/qt5.rc &&

if module_installed qwt-6 ; then
  LDFLAGS+=" -Wl,-rpath,/usr/lib/qwt-6/" &&
  OPTS+=" -DQWT_INCLUDE_DIR=/usr/include/qwt \
          -DQWT_LIBRARY=/usr/lib/qwt-6/libqwt.so"
fi &&

OPTS+=" -DQSCINTILLA_INCLUDE_DIR=/usr/include/qt5/ \
        -DQSCINTILLA_LIBRARY=/usr/lib/qt5/libqscintilla2_qt5.so \
        -DQCA_INCLUDE_DIR=/usr/include/qt5/Qca-qt5/QtCrypto \
        -DQCA_LIBRARY=/usr/lib/qt5/libqca-qt5.so \
        -DWITH_QSPATIALITE=ON \
        -DWITH_QUICK=ON \
        -DQWT_POLAR_VERSION=0x060200 \
        -DWITH_CUSTOM_WIDGETS=ON \
        -DWITH_APIDOC=OFF \
        -DWITH_QTWEBKIT=OFF \
        -DHAS_KDE_QT5_PDF_TRANSFORM_FIX=ON \
        -DHAS_KDE_QT5_SMALL_CAPS_FIX=ON \
        -DHAS_KDE_QT5_FONT_STRETCH_FIX=ON \
        -DWITH_3D=ON"


default_cmake_build
