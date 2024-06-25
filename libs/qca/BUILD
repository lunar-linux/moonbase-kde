export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_TESTS=OFF \
        -Wno-dev \
        -DQCA_INSTALL_IN_QT_PREFIX=ON \
        -DCMAKE_BUILD_TYPE=Release"

if in_depends $MODULE qt5; then
  source /etc/profile.d/qt5.rc &&
  cmake -B $MODULE-qt5 -S . -G Ninja $OPTS -DBUILD_WITH_QT6=OFF &&
  cmake --build $MODULE-qt5
fi &&

prepare_install &&

if in_depends $MODULE qt5; then
  cmake --install $MODULE-qt5
fi
