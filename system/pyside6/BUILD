source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

CLANG_INSTALL_DIR="/usr" \
OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=None \
        -DSHIBOKEN_PYTHON_LIBRARIES=`pkgconf python3-embed --libs` \
        -DBUILD_TESTS=OFF \
        -DFORCE_LIMITED_API=OFF \
        -DNO_QT_TOOLS=ON"

cmake -B $MODULE-$VERSION -S . -G Ninja PYTHONPATH=build/sources $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION/sources/pyside6 &&
cmake --install $MODULE-$VERSION/sources/pyside-tools &&
cmake --install $MODULE-$VERSION/sources/shiboken6
