source /etc/profile.d/qt6.rc &&

sedit 's|plugins/gammaray|lib/qt6/plugins/gammaray|' CMakeLists.txt &&

OPTS+=" -DGAMMARAY_INSTALL_QT_LAYOUT=ON \
        -DQT_VERSION_MAJOR=6 \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DSTACK_DETAILS_DWARF=ON \
        -DLIBDWARF_INCLUDE_DIR=/usr/include/libdwarf-0 \
        -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt6/mkspecs/modules \
        -DPLUGIN_INSTALL_DIR=/usr/lib/qt6/plugins/gammaray" &&

default_cmake_build
