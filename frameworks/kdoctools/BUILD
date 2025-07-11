source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_PREFIX_PATH=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_WITH_QT6=ON \
        -DDocBookXSL_DIR=/usr/share/sgml/docbook/xsl-stylesheets-`lvu version docbook-xsl` \
        -DDocBookXML4_DTD_DIR=/usr/share/sgml/docbook/xml/4.5 \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
