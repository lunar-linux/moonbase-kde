source /etc/profile.d/qt6.rc &&

export QMAKEFEATURES+=" src/features/" &&

cd src &&
  export QMAKEFEATURES &&
  /usr/lib/qt6/bin/qmake &&
  default_make &&

cd ../designer &&
  /usr/lib/qt6/bin/qmake INCLUDEPATH+=../src QMAKE_LIBDIR+=../src &&
  default_make &&

cd ../Python
  cp pyproject-qt6.toml pyproject.toml &&
  sip-build \
    --no-make \
    --qsci-features-dir ../src/features \
    --qsci-include-dir ../src \
    --qsci-library-dir ../src \
    --api-dir /usr/share/qt6/qsci/api/python &&
  cd build &&
  default_make &&

cd ../../src &&

default_make
