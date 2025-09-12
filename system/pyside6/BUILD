source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

CLANG_INSTALL_DIR="/usr" \
OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DSHIBOKEN_PYTHON_LIBRARIES=$(pkgconf python3-embed --libs) \
        -DBUILD_TESTS=ON \
        -DFORCE_LIMITED_API=no \
        -DNO_QT_TOOLS=no"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION/sources/shiboken6 &&
cmake --install $MODULE-$VERSION/sources/pyside6 &&
cmake --install $MODULE-$VERSION/sources/pyside-tools &&

TYPESYSTEM_SRC="$MODULE-$VERSION/sources/pyside6/PySide6" &&

cp "$TYPESYSTEM_SRC"/typesystem_*.xml /usr/share/PySide6/typesystems/ 2>/dev/null || true &&

chmod 644 /usr/share/PySide6/typesystems/typesystem_*.xml
