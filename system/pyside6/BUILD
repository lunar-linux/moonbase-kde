source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

CLANG_INSTALL_DIR="/usr" \
OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=lib \
        -DCMAKE_BUILD_TYPE=Release \
        -DSHIBOKEN_PYTHON_LIBRARIES=$(pkgconf python3-embed --libs) \
        -DBUILD_TESTS=OFF \
        -DFORCE_LIMITED_API=no \
        -DNO_QT_TOOLS=yes"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

export PATH="/usr/lib/qt6/:$PATH"
python setup.py egg_info --build-type=shiboken6 &&
python setup.py egg_info --build-type=shiboken6-generator &&
_pythonpath=`python -c "from sysconfig import get_path; print(get_path('platlib'))"` &&
cp -r shiboken6*.egg-info $_pythonpath &&

prepare_install
cmake --install $MODULE-$VERSION/sources/shiboken6 &&
cmake --install $MODULE-$VERSION/sources/pyside6 &&
cmake --install $MODULE-$VERSION/sources/pyside-tools &&

python setup.py egg_info --build-type=pyside6 &&
_pythonpath=`python -c "from sysconfig import get_path; print(get_path('platlib'))"` &&
cp -r PySide6.egg-info $_pythonpath &&

#Fix pathing for tyepsystems
sedit 's|/typesystems|/share/PySide6/typesystems|' /usr/lib/cmake/PySide6/PySide6Config.cpython-312-x86_64-linux-gnu.cmake
sedit 's:/glue:/share/PySide6/glue:' /usr/lib/cmake/PySide6/PySide6Config.cpython-312-x86_64-linux-gnu.cmake
