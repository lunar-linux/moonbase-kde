source /etc/profile.d/qt5.rc &&

OPTS+=" -Dkst_release=1 \
        -Dkst_qt5=1    \
        -Dkst_merge_files=ON \
        -Dkst_install_libdir=/usr/lib \
        -Dkst_install_prefix=/usr \
        -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
