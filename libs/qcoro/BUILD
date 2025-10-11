source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_SHARED_LIBS=ON -Wno-dev"

cmake -B $MODULE-qt6 -S . $OPTS -DUSE_QT_VERSION=6 -DCMAKE_INSTALL_PREFIX=/usr -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt6/mkspecs/modules/ &&
cmake --build $MODULE-qt6 &&
prepare_install &&
cmake --install $MODULE-qt6

