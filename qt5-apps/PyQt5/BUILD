
  . /etc/profile.d/qt5.rc &&

  sedit "s:qprinter.h:QtPrintSupport/qprinter.h:" sip/QtPrintSupport/qprinter.sip &&

  python configure.py --confirm-license -w $OPTS &&

  default_make
