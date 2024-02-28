source /etc/profile.d/qt5.rc &&
/usr/lib/qt5/bin/qmake $OPTS &&
default_make &&

if in_depends $MODULE qt6-tools; then
  source /etc/profile.d/qt6.rc &&
  /usr/lib/qt6/bin/qmake6 PREFIX=/usr LIBDIR=/usr/lib $OPTS &&
  default_make
fi
