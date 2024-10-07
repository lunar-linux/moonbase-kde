OPTS+=" -DCMAKE_BUILD_TYPE=Release -DBUILD_SHARED_LIBS=ON -Wno-dev"

if in_depends $MODULE qt5;then
 source /etc/profile.d/qt5.rc &&
 cmake -B $MODULE-qt5 -S . $OPTS -DUSE_QT_VERSION=5 -DCMAKE_INSTALL_PREFIX=/usr -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt5/mkspecs/modules/ &&
 cmake --build $MODULE-qt5 &&
 prepare_install &&
 cmake --install $MODULE-qt5
fi &&

if in_depends $MODULE qt6-websockets; then
 source /etc/profile.d/qt6.rc &&
 cmake -B $MODULE-qt6 -S . $OPTS -DUSE_QT_VERSION=6 -DCMAKE_INSTALL_PREFIX=/usr -DECM_MKSPECS_INSTALL_DIR=/usr/lib/qt6/mkspecs/modules/ &&
 cmake --build $MODULE-qt6 &&
 prepare_install &&
 cmake --install $MODULE-qt6
fi

