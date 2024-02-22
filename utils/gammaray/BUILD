. /etc/profile.d/qt5.rc &&

sedit 's|plugins/gammaray|lib/qt5/plugins/gammaray|' CMakeLists.txt &&

OPTS+=" -DGAMMARAY_INSTALL_QT_LAYOUT=ON \
        -DQT_VERSION_MAJOR=5 \
        -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt5/mkspecs/modules \
        -DPLUGIN_INSTALL_DIR=/usr/lib/qt5/plugins/gammaray" &&

default_cmake_build
