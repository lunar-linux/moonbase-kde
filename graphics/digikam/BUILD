. /etc/profile.d/qt5.rc &&

sedit 's:Akonadi/Contact/:AkonadiContact/Akonadi/:' core/utilities/extrasupport/addressbook/akonadiiface.cpp &&

OPTS+=" -DENABLE_AKONADICONTACTSUPPORT=ON \
        -DENABLE_KFILEMETADATASUPPORT=ON \
        -DENABLE_MEDIAPLAYER=ON \
        -DENABLE_APPSTYLES=ON \
        -DENABLE_QWEBENGINE=ON \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON" &&

if module_installed ccache ; then
  OPTS+=" -DBUILD_WITH_CCACHE=ON"
fi &&

default_cmake_build
