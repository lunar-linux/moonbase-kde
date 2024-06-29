source /etc/profile.d/qt6.rc &&

OPTS+=" -DENABLE_AKONADICONTACTSUPPORT=ON \
        -DENABLE_KFILEMETADATASUPPORT=ON \
        -DENABLE_MEDIAPLAYER=ON \
        -DENABLE_APPSTYLES=ON \
        -DBUILD_WITH_QT6=ON   \
        -DENABLE_QWEBENGINE=ON" &&

if module_installed ccache ; then
  OPTS+=" -DBUILD_WITH_CCACHE=ON"
fi &&

default_cmake_build
