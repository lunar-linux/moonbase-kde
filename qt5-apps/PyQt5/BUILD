
  . /etc/profile.d/qt5.rc &&

# sip: Deprecation warning: the -T flag is ignored and deprecated
  sedit "s:-T::" configure.py &&

# Thanks to the arch folks for finding this, it had trouble finding
# /usr/lib/dbus-1.0/include/dbus/dbus-arch-deps.h
  sed -i '/target_config.dbus_inc_dirs = \[\]/d' configure.py &&

  sedit "s:qprinter.h:QtPrintSupport/qprinter.h:" sip/QtPrintSupport/qprinter.sip &&


  OPTS+=" --confirm-license --qmake=/usr/lib/qt5/bin/qmake --assume-shared --no-timestamp" &&

  if module_installed qscintilla2 ; then
    OPTS+=" --qsci-api"
  fi &&

  python configure.py -w $OPTS -j${MAKES} &&
  find -name 'Makefile' | xargs sed -i 's|-Wl,-rpath,/usr/lib||g;s|-Wl,-rpath,.* ||g' &&
  default_make &&

# Now the Python-3 stuff
  if in_depends $MODULE Python-3 ; then
    python3 configure.py -w $OPTS -j${MAKES} &&
    find -name 'Makefile' | xargs sed -i 's|-Wl,-rpath,/usr/lib||g;s|-Wl,-rpath,.* ||g' &&
    default_make
  fi
