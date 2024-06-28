source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

#Need the marble tools else libkgeomap tanks missing Astro
OPTS+=" -DCMAKE_INSTALL_SYSCONFDIR=/etc \
        -DBUILD_MARBLE_TOOLS=ON         \
        -DBUILD_MARBLE_EXAMPLES=OFF     \
        -DBUILD_MARBLE_TESTS=OFF        \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DMOBILE=OFF"

default_cmake_build
