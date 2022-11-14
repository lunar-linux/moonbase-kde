ulimit -u 8192 &&

source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DQT_BUILD_EXAMPLES_BY_DEFAULT=OFF \
        -DQT_BUILD_TESTS_BY_DEFAULT=OFF \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DINSTALL_BINDIR=lib/qt6/bin \
        -DINSTALL_LIBEXECDIR=/usr/lib/qt6 \
        -DINSTALL_LIBDIR=lib/qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=/usr/lib/qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=lib/qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DINSTALL_SYSCONFDIR=/etc/xdg \
        -DQT_FEATURE_webengine_system_libevent=ON \
        -DQT_FEATURE_webengine_system_ffmpeg=ON \
        -DQT_FEATURE_webengine_system_icu=OFF \
        -DQT_FEATURE_webengine_kerberos=ON \
        -DQT_FEATURE_webengine_proprietary_codecs=ON \
        -DQT_FEATURE_webengine_webrtc_pipewire=ON"

cmake -B build -S . -G Ninja -Wno-dev $OPTS &&

cmake --build build &&
prepare_install &&
cmake --install build
