. /etc/profile.d/qt6.rc &&

#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_TESTS=0 \
        -DQT6=ON \
        -DBUILD_WITH_QT6=ON \
        -DBUILD_TOOLS=ON \
        -DQCA_FEATURE_INSTALL_DIR=/usr/lib/qt6/mkspecs/features \
        -DQCA_PLUGINS_INSTALL_DIR=/usr/lib/qt6/plugins"

default_cmake_build
