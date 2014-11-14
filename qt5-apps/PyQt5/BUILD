
  . /etc/profile.d/qt5.rc &&

  sedit "s:qprinter.h:QtPrintSupport/qprinter.h:" sip/QtPrintSupport/qprinter.sip &&

  OPTS+=" --confirm-license --qmake=/usr/lib/qt5/bin/qmake --assume-shared --no-timestamp" &&

  if module_installed qscintilla2 ; then
    OPTS+=" --qsci-api"
  fi &&

  python configure.py -w $OPTS -j${MAKES} &&
  default_make &&

# Now the Python-3 stuff
  if in_depends $MODULE Python-3 ; then
    python3 configure.py -w $OPTS -j${MAKES} &&
    default_make
  fi
