
  source /etc/profile.d/qt5.rc &&

#  for i in `ls src/*.h` ; do sedit "s:qwt_global.h :qwt-6/qwt_global.h:" $i ; done &&

  sedit "s:/usr/local/qwt-\$\$QWT_VERSION:/usr:" qwtconfig.pri &&
  sedit "s:/doc:/share/doc/$MODULE:" qwtconfig.pri &&
  sedit "s:/include:/include/qwt:" qwtconfig.pri &&
  sedit "s:/lib:/lib/$MODULE:" qwtconfig.pri &&
  sedit "s:plugins/designer:/lib/$MODULE/plugins/designer/$MODULE:" qwtconfig.pri &&
  sedit "s:\$\${QWT_INSTALL_PREFIX}/features:/usr/share/$MODULE/mkspecs/features:" qwtconfig.pri &&
  sedit "s:plugins/designer:plugins/designer/$MODULE:" designer/designer.pro &&

  /usr/lib/qt5/bin/qmake &&
  default_make
