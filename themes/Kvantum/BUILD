# Fix Qt6 build with Qt5 installed
sed -e 's|Qt6 Qt5|Qt6|' -i Kvantum/*/CMakeLists.txt &&
# Build manager with Qt6
sed -e 's|if(ENABLE_QT5)|if(TRUE)|' -i Kvantum/CMakeLists.txt &&

source /etc/profile.d/qt6.rc &&
cmake -B $MODULE-qt6 -S $MODULE -DENABLE_QT5=OFF $OPTS &&
cmake --build $MODULE-qt6 &&

prepare_install &&
cmake --install $MODULE-qt6

