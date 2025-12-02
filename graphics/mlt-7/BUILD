source /etc/profile.d/qt6.rc  &&

if in_depends $MODULE tcl; then
  OPTS+=" -DTK_LIBRARY=/usr/lib"
fi &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr\
        -DCMAKE_BUILD_TYPE=Release \
        -DMOD_GLAXNIMATE=OFF \
        -DMOD_GLAXNIMATE_QT6=OFF \
        -DMOD_QT=OFF \
        -DMOD_SDL1=OFF \
        -DMOD_QT6=ON \
        -DMOD_MOVIT=OFF \
        -DMOD_SPATIALAUDIO=OFF \
        -DMOD_RESAMPLE=OFF \
        -DSWIG_CSHARP=OFF \
        -DBUILD_TESTS_WITH_QT6=OFF \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&

cmake --install $MODULE-$VERSION
