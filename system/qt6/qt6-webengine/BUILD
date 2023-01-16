ulimit -u 8192 &&

source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DQT_BUILD_EXAMPLES_BY_DEFAULT=OFF \
        -DQT_BUILD_TESTS_BY_DEFAULT=OFF \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DINSTALL_LIBEXECDIR=qt6 \
        -DINSTALL_LIBDIR=qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=lib/qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_SYSCONFDIR=/etc/xdg \
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
