source /etc/profile.d/qt6.rc &&

export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -DQT_BUILD_EXAMPLES_BY_DEFAULT=OFF \
        -DQT_BUILD_TESTS_BY_DEFAULT=OFF \
        -DQT_UNITY_BUILD=OFF \
        -DQT_INSTALL_EXAMPLES_SOURCES_BY_DEFAULT=OFF \
        -DQT_FEATURE_webengine_system_libevent=ON \
        -DQT_FEATURE_webengine_system_icu=ON \
        -DQT_FEATURE_webengine_webrtc_pipewire=ON    \
        -DQT_FEATURE_webengine_proprietary_codecs=ON \
        -DQT_FEATURE_webengine_kerberos=ON \
        -DCMAKE_TOOLCHAIN_FILE=/usr/lib/qt6/cmake/Qt6/qt.toolchain.cmake \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
# Remove point to the src build direcotry
find $MODULE-$VERSION/qt6 -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake --install $MODULE-$VERSION
