source /etc/profile.d/qt6.rc &&

export QMAKEFEATURES+=" src/features/" &&

cd src &&
  export QMAKEFEATURES &&
  /usr/lib/qt6/bin/qmake6 &&
  make &&

cd ../designer &&
  /usr/lib/qt6/bin/qmake6 INCLUDEPATH+=../src QMAKE_LIBDIR+=../src &&
  make &&

cd ../Python &&
  mv pyproject-qt6.toml pyproject.toml &&
  sip-build \
    --no-make \
    --qsci-features-dir ../src/features \
    --qsci-include-dir ../src \
    --qsci-library-dir ../src \
    --api-dir /usr/share/qt6/qsci/api/python \
    --qmake=/usr/lib/qt6/bin/qmake6 &&
  cd build &&
  make &&

#cd ../../src &&

default_make
