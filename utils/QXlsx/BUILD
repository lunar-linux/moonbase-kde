sedit '20i if(Qt6Gui_VERSION VERSION_GREATER_EQUAL "6.10.0") \
    find_package(Qt6 REQUIRED COMPONENTS GuiPrivate)\
endif()' QXlsx/CMakeLists.txt

source /etc/profile.d/qt6.rc &&

OPTS+=" -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DCMAKE_BUILD_TYPE=Release \
        -DQT_VERSION_MAJOR=6 \
        -DBUILD_SHARED_LIBS=ON \
        -Wno-dev "

cmake -B $MODULE-$VERSION -S QXlsx -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
