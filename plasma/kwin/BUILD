#The .clang-format file already exists.  Please remove it in order to use
#the file provided by ECM
rm .clang-format &&

source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DBUILD_WITH_QT6=ON -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

default_cmake_build
