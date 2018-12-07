source /etc/profile.d/qt5.rc &&

export CXXFLAGS+=" -I../Qt4Qt5" &&
export LDFLAGS+=" -L../Qt4Qt5" &&
export QMAKEFEATURES+=" Qt4Qt5/features/" &&

pushd Qt4Qt5 > /dev/null &&
  /usr/lib/qt5/bin/qmake qscintilla.pro &&
  default_make
popd > /dev/null &&

pushd designer-Qt4Qt5 > /dev/null &&
  /usr/lib/qt5/bin/qmake designer.pro INCLUDEPATH+=../Qt4Qt5 QMAKE_LIBDIR+=../Qt4Qt5 &&
  default_make
popd > /dev/null &&

# install the Python3 bindings
pushd Python > /dev/null &&
  python3 configure.py --pyqt=PyQt5 -n ../Qt4Qt5/ -o ../Qt4Qt5/ -c --qmake /usr/lib/qt5/bin/qmake &&
  default_make &&
  install sip/*.sip /usr/share/sip/PyQt5/Qsci
popd > /dev/null &&

# install the Python2 bindings
if module_installed python2; then
  pushd Python > /dev/null &&
    rm -rf ../qscsi &&
    python2 configure.py --pyqt=PyQt5 -n ../Qt4Qt5/ -o ../Qt4Qt5/ -c --qmake /usr/lib/qt5/bin/qmake &&
    default_make
  popd > /dev/null
fi &&

# Some programs may look for this
ln -sfv /usr/lib/qt5/libqscintilla2_qt5.so /usr/lib/qt5/libqt5scintilla2.so
