source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

sedit '17i #include <QRegularExpression>' texttranslator/translator/plugins/google/googleengineplugin.cpp &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DQT_MAJOR_VERSION=6 \
        -Wno-dev"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS &&
cmake --build $MODULE-$VERSION &&

prepare_install
cmake --install $MODULE-$VERSION
