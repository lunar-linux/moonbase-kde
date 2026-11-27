source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -Wno-author"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION &&

cp src/resources/qgit.svg /usr/share/icons/hicolor/scalable/apps/ &&
cp src/resources/qgit.png /usr/share/icons/hicolor/48x48/apps/
