source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Release -Wno-dev"

cmake -B $MODULE-qt6 -S $MODULE -DENABLE_QT5=OFF $OPTS &&
cmake --build $MODULE-qt6 &&

prepare_install &&
cmake --install $MODULE-qt6

