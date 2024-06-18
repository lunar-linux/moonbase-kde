#See; https://bugs.gentoo.org/930107
#sedit '199i "//components/spellcheck:buildflags",' src/3rdparty/chromium/content/browser/BUILD.gn &&
#sedit '238i "//components/web_cache/public/mojom",' src/3rdparty/chromium/content/browser/BUILD.gn &&

source /etc/profile.d/qt6.rc &&

# uses malloc_usable_size, which is incompatible with fortification level 3
export CFLAGS="${CFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"
export CXXFLAGS="${CXXFLAGS/_FORTIFY_SOURCE=3/_FORTIFY_SOURCE=2}"

#Generating .rcc/qmlcache/qtgraphicaleffectsplugin_ColorOverlay_qml.cpp
#Detected locale "en_US" with character encoding "ISO-8859-1", which is not UTF-8.
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -DQT_BUILD_EXAMPLES_BY_DEFAULT=OFF \
        -DQT_FEATURE_webengine_system_libevent=ON \
        -DQT_FEATURE_webengine_system_ffmpeg=ON \
        -DQT_FEATURE_webengine_system_icu=ON \
        -DQT_FEATURE_webengine_webrtc_pipewire=ON    \
        -DQT_FEATURE_webengine_proprietary_codecs=ON \
        -DCMAKE_TOOLCHAIN_FILE=/usr/lib/qt6/cmake/Qt6/qt.toolchain.cmake \ 
        -DINSTALL_GN=OFF \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&

cmake --build $MODULE-$VERSION &&
prepare_install &&

# Remove point to the src build direcotry
find $MODULE-$VERSION/qt6 -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake --install $MODULE-$VERSION
