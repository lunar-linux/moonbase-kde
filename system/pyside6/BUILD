source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'
export PYTHONDONTWRITEBYTECODE=1 

#git revert -n d252378a3980c99e23340e6b722631182814d8bb 71c4d1750463c99ab9cbff7e1d7162210506f225 &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DSHIBOKEN_PYTHON_LIBRARIES=$(pkgconf python3-embed --libs) \
        -DBUILD_TESTS=OFF \
        -DFORCE_LIMITED_API=OFF \
        -DNO_QT_TOOLS=no"

cmake -B $MODULE-$VERSION -S . -G Ninja PYTHONPATH="$PWD"/build/sources $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION/sources/shiboken6 &&
cmake --install $MODULE-$VERSION/sources/shiboken6_generator &&
cmake --install $MODULE-$VERSION/sources/pyside6 &&
cmake --install $MODULE-$VERSION/sources/pyside-tools

## pyside6.pc
#sedit 's|/usr/PySide6/include|/usr/include/PySide6|' /usr/lib/pkgconfig/pyside6.pc
