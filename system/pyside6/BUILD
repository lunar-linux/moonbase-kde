source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'
export PYTHONPATH="$PWD"/$MODULE-$VERSION/sources

OPTS+=" -DCMAKE_INSTALL_LIBDIR=lib \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=None \
        -DPython_EXECUTABLE=/usr/bin/python \
        -DSHIBOKEN_PYTHON_LIBRARIES=`pkgconf python3-embed --libs` \
        -DBUILD_TESTS=OFF \
        -DFORCE_LIMITED_API=OFF \
        -DSPHINX_BUILD=OFF  \
        -DNO_QT_TOOLS=ON \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS $PYTHONPATH &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
