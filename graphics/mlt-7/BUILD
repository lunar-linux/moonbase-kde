source /etc/profile.d/qt6.rc  &&

if in_depends $MODULE tcl; then
  OPTS+=" -DTK_LIBRARY=/usr/lib"
fi &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr\
        -DCMAKE_BUILD_TYPE=Release \
        -DMOD_GLAXNIMATE_QT6=OFF \
        -DMOD_QT6=ON \
        -DSWIG_CSHARP=OFF \
        -DMOD_MOVIT=OFF \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&

cmake --install $MODULE-$VERSION
