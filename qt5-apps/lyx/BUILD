if in_depends $MODULE qt5; then
  . /etc/profile.d/qt5.rc &&
  QTDIR+=" QTDIR=/usr/lib/qt5" &&
  QT_UIC+=" /usr/lib/qt5/bin/uic" &&
  QT_MOC+=" /usr/lib/qt5/bin/moc"
else
  . /etc/profile.d/qt4.rc
fi &&

default_build
