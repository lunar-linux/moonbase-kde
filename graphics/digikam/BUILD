
. /etc/profile.d/qt4.rc  &&
. /etc/profile.d/kde4.rc &&

# https://bugs.gentoo.org/show_bug.cgi?id=566624
sedit "27,28d" core/libs/dimg/filters/lens/lensfuniface.h &&
sedit "28d" core/libs/dimg/filters/lens/lensfuniface.h &&

#Disabling for now
sedit "s:add_subdirectory(panorama)::" extra/kipi-plugins/CMakeLists.txt &&

if in_depends $MODULE qca2; then
  sedit "s:QtCrypto:Qca-qt4/QtCrypto/QtCrypto:" extra/kipi-plugins/shwup/swconnector.cpp extra/kipi-plugins/yandexfotki/yandexauth.cpp &&
  OPTS+=" -DQCA2_INCLUDE_DIR=/usr/include/Qca-qt4 -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2"
fi &&

OPTS+=" -DDIGIKAMSC_COMPILE_LIBKGEOMAP=1   \
        -DDIGIKAMSC_COMPILE_LIBMEDIAWIKI=1 \
        -DDIGIKAMSC_COMPILE_LIBKFACE=0     \
        -DENABLE_BALOOSUPPORT=0            \
        -DBUILD_tests=0                    \
        -DCMAKE_SKIP_RPATH=1               \
        -DKDE4_BUILD_TESTS=0" &&

if in_depends $MODULE kQOAuth-qt4 ; then
  OPTS+=" -DQTKOAUTH_INCLUDE_DIR=/usr/include/QtKOAuth-qt4 -DQTKOAUTH_LIBRARIES=/usr/lib/qt4/libkqoauth-qt4.so"
fi &&

default_cmake_build
