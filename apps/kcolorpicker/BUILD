source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_SHARED_LIBS=ON -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release -Wno-dev"

cmake -B $MODULE-$VERSION-qt6 -S . -DBUILD_WITH_QT6=ON $OPTS &&
cmake --build $MODULE-$VERSION-qt6 &&

if in_depends $MODULE qt5; then
  source /etc/profile.d/qt5.rc &&
  cmake -B $MODULE-$VERSION-qt5 -S . $OPTS &&
  cmake --build $MODULE-$VERSION-qt5
fi &&

prepare_install &&
cmake --install $MODULE-$VERSION-qt6 &&

if in_depends $MODULE qt5; then
cmake --install $MODULE-$VERSION-qt5
fi
