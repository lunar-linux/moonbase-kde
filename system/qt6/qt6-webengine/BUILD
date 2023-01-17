ulimit -u 8192 &&

source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DINSTALL_LIBDIR=lib/qt6 \
        -DQT_FEATURE_webengine_system_libevent=ON \
        -DQT_FEATURE_webengine_system_ffmpeg=ON \
        -DQT_FEATURE_webengine_system_icu=ON \
        -DQT_FEATURE_webengine_kerberos=ON \
        -DQT_FEATURE_webengine_proprietary_codecs=ON \
        -DQT_FEATURE_webengine_webrtc_pipewire=ON"

cmake -B build -S . -G Ninja -Wno-dev $OPTS &&

cmake --build build &&
prepare_install &&

# Remove point to the src build direcotry
find build/qt6 -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake --install build
