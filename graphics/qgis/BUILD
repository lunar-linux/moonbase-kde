source /etc/profile.d/qt6.rc &&

OPTS+=" -DQSCINTILLA_INCLUDE_DIR=/usr/lib/include/qt6/ \
        -DQSCINTILLA_LIBRARY=/usr/lib/qt6/libqscintilla2_qt6.so \
        -DQCA_INCLUDE_DIR=/usr/include//Qca-qt6/QtCrypto \
        -DQCA_LIBRARY=/usr/lib/libqca-qt6.so \
        -DWITH_QSPATIALITE=ON \
        -DWITH_QUICK=ON \
        -DWITH_CUSTOM_WIDGETS=ON \
        -DWITH_APIDOC=OFF \
        -DWITH_QTWEBKIT=OFF \
        -DHAS_KDE_QT5_PDF_TRANSFORM_FIX=ON \
        -DHAS_KDE_QT5_SMALL_CAPS_FIX=ON \
        -DHAS_KDE_QT5_FONT_STRETCH_FIX=ON \
        -DWITH_3D=ON \
        -DWITH_DRACO=OFF \
        -DWITH_PDAL=OFF \
        -DQWT_INCLUDE_DIR=/usr/include/qwt \
        -DQWT_LIBRARY=/usr/lib/libqwt.so \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DWITH_INTERNAL_SPATIALINDEX=ON \
        -DWITH_QSPATIALITE=OFF \
        -DBUILD_WITH_QT6=ON \
        -Wno-dev"


cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
