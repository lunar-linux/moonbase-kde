. /etc/profile.d/qt5.rc &&

OPTS+=" -DENABLE_AKONADICONTACTSUPPORT=1 \
        -DENABLE_KFILEMETADATASUPPORT=1 \
        -DENABLE_MEDIAPLAYER=1 \
        -DENABLE_APPSTYLES=1 \
        -DENABLE_QWEBENGINE=1 \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

if module_installed ccache ; then
  OPTS+=" -DBUILD_WITH_CCACHE=ON"
fi &&

default_cmake_build
