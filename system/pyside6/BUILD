source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

git revert -n c9d602ab4afa5c9834c4674a742dc9bab7f4b326 05e328476f2d6ef8a0f3f44aca1e5b1cdb7499fc &&

#This needs done after the above git reverts
patch -p1 < $SCRIPT_DIRECTORY/001-fix-header-install-dir.patch &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DSHIBOKEN_PYTHON_LIBRARIES=$(pkgconf python3-embed --libs) \
        -DBUILD_TESTS=OFF \
        -DFORCE_LIMITED_API=OFF \
        -DNO_QT_TOOLS=no"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION/sources/shiboken6 &&
cmake --install $MODULE-$VERSION/sources/shiboken6_generator &&
cmake --install $MODULE-$VERSION/sources/pyside6 &&
cmake --install $MODULE-$VERSION/sources/pyside-tools

# pyside6.pc
sedit 's|/usr/PySide6/include|/usr/include/PySide6|' /usr/lib/pkgconfig/pyside6.pc
