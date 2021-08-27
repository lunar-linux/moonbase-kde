. /etc/profile.d/qt5.rc &&

export QMAKEFEATURES+=" src/features/" &&

cd src &&
  export QMAKEFEATURES &&
  /usr/lib/qt5/bin/qmake &&
  make &&

cd ../designer &&
  /usr/lib/qt5/bin/qmake INCLUDEPATH+=../src QMAKE_LIBDIR+=../src &&
  make &&

cd ../Python
  cp pyproject-qt5.toml pyproject.toml &&
  sip-build \
    --no-make \
    --qsci-features-dir ../src/features \
    --qsci-include-dir ../src \
    --qsci-library-dir ../src \
    --api-dir /usr/share/qt/qsci/api/python &&
  cd build &&
  make

cd ../../src &&

default_make
