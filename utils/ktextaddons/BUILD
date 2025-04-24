source /etc/profile.d/qt6.rc &&

sedit '17i #include <QRegularExpression>' texttranslator/translator/plugins/google/googleengineplugin.cpp &&

OPTS+=" -DQT_MAJOR_VERSION=6 -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

default_cmake_build
