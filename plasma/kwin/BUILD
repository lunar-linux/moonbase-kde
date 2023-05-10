source /etc/profile.d/qt5.rc &&

# cmake configure notes this file should be removed to use the one
# provided by extra-cmake-modules.
rm -rf .clang-format &&

OPTS+=" -DCMAKE_INSTALL_LIBEXECDIR=lib" &&

default_cmake_build
