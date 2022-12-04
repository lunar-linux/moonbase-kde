. /etc/profile.d/qt5.rc &&

#Need the marble tools else libkgeomap tanks missing Astro
OPTS+=" -DCMAKE_INSTALL_SYSCONFDIR=/etc   \
        -DBUILD_MARBLE_EXAMPLES=ON        \
        -DBUILD_MARBLE_TESTS=OFF          \
        -DMOBILE=OFF                      "

default_cmake_build
