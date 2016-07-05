. /etc/profile.d/qt5.rc  &&

# Build borks on some translation stuff
sedit "s:add_subdirectory(showfoto)::" doc-translated/digikam/CMakeLists.txt &&

OPTS+=" -DDIGIKAMSC_COMPILE_LIBKIPI=1      \
        -DDIGIKAMSC_COMPILE_LIBKSANE=1     \
        -DDIGIKAMSC_COMPILE_LIBMEDIAWIKI=1 \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=1"  &&

default_cmake_build
