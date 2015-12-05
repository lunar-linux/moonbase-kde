. /etc/profile.d/qt4.rc  &&
. /etc/profile.d/kde4.rc &&

# https://bugs.gentoo.org/show_bug.cgi?id=566624
sedit "27,28d" core/libs/dimg/filters/lens/lensfuniface.h &&
sedit "28d" core/libs/dimg/filters/lens/lensfuniface.h &&

#Disabling for now
sedit "s:add_subdirectory(panorama)::" extra/kipi-plugins/CMakeLists.txt &&

OPTS+=" -DBUILD_tests=0" &&

# Disabling these here else the digikam provided ones will conflict
# with the ones from kde.
OPTS+=" -DDIGIKAMSC_COMPILE_LIBKDCRAW=0 \
        -DDIGIKAMSC_COMPILE_LIBKEXIV2=0 \
        -DDIGIKAMSC_COMPILE_LIBKFACE=0  \
        -DDIGIKAMSC_COMPILE_LIBKIPI=0   \
        -DDIGIKAMSC_COMPILE_LIBKSANE=0" &&

if in_depends $MODULE kQOAuth ; then
  OPTS+=" -DQTKOAUTH_INCLUDE_DIR=/usr/include/QtKOAuth-qt4 -DQTKOAUTH_LIBRARIES=/usr/lib/qt4"
fi &&

default_cmake_build
