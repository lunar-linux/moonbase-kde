. /etc/profile.d/qt5.rc &&

sedit '8i #include <cstdint>' cmemorymappedfile.h &&

qmake-qt5 QMAKE_CFLAGS="${CFLAGS}" \
          QMAKE_CXXFLAGS="${CXXFLAGS}" \
          CONFIG+=release \
          CONFIG+=c++14  \
          $OPTS &&

default_make
