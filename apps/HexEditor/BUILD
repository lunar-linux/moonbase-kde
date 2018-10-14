. /etc/profile.d/qt5.rc &&

qmake-qt5 QMAKE_CFLAGS="${CFLAGS}" \
          QMAKE_CXXFLAGS="${CXXFLAGS}" \
          CONFIG+=release \
          CONFIG+=c++14  \
          $OPTS &&

default_make
