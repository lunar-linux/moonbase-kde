source /etc/profile.d/qt5.rc &&

sedit 's:include/hdf5:include:' cmake/modules/FindHDF5.cmake &&

OPTS+=" -Dkst_release=1 \
        -Dkst_qt5=1    \
        -Dkst_python=1 \
        -Dkst_install_libdir=lib \
        -Dkst_install_prefix=/usr"

cmake -B $MODULE-$VERSION -S . $OPTS -DCMAKE_POLICY_VERSION_MINIMUM=3.5 &&
cmake --build $MODULE-$VERSION &&

prepare_install &&
cmake --install $MODULE-$VERSION
