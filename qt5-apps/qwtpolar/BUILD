
  source /etc/profile.d/qt5.rc  &&

  echo "INCLUDEPATH += /usr/include/qwt" >> qwtpolarbuild.pri &&
  sed -i -e 's/^.*QwtPolarExamples//' qwtpolarconfig.pri &&
  sed -i -e 's/$${QWT_POLAR_INSTALL_PREFIX}\/doc/\/usr\/share\/doc\/qwt\//' qwtpolarconfig.pri &&
  sed -i -e 's/$${QWT_POLAR_INSTALL_PREFIX}\/include/\/usr\/include\/qwt\//' qwtpolarconfig.pri &&
  sed -i -e 's/$${QWT_POLAR_INSTALL_PREFIX}\/lib/\/usr\/lib\//' qwtpolarconfig.pri &&
  sed -i -e 's/$${QWT_POLAR_INSTALL_PREFIX}\/features/\/usr\/share\/qwt\/features\//' qwtpolarconfig.pri &&
  sed -i -e 's/^.*QwtPolarDesigner//' qwtpolarconfig.pri &&

  /usr/lib/qt5/bin/qmake qwtpolar.pro &&

  default_make
