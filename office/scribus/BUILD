. /etc/profile.d/qt5.rc &&

OPTS+=" -DCMAKE_BUILD_TYPE=Releas -Wno-dev -DCMAKE_INSTALL_PREFIX=/usr -DPython3_EXECUTABLE=python3 -DWANT_HEADERINSTALL=ON -DWANT_NOEXAMPLES==ON -DWANT_CPP17=ON "
 
cmake -B $MODULE-$VERSION -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&
prepare_install &&
cmake --install $MODULE-$VERSION
