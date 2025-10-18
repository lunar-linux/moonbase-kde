source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_CXX_STANDARD=17 \
        -DCMAKE_C_STANDARD=17   \
        -DCMAKE_C_COMPILER=gcc \
        -DCMAKE_CXX_COMPILER=g++ \
        -DCMAKE_C_EXTENSIONS=ON \
        -DENABLE_QT6=ON \
        -DPREFER_SYSTEM_INDILIB=NO \
        -DCMAKE_CXX_EXTENSIONS=ON \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
        -DENABLE_XLSX=OFF \
        -Wno-dev"

cmake -S . -B $MODULE-build -G Ninja $OPTS &&
cmake --build $MODULE-build --target all &&

prepare_install &&
cmake --build $MODULE-build --target install
