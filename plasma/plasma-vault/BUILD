source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

sedit '8i #include <QDebug>' kded/engine/commandresult.cpp &&

default_cmake_build
