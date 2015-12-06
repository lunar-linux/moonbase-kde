
  source /etc/profile.d/qt4.rc &&

  OPTS+=" --include-paths=/usr/include/qt4" &&

# A qucik gcc-4.4.1 hack. Revisit when this module gets a version bump
  sed -i "33i #include <cstdio>" generator/parser/rpp/pp.h &&

# sed this out so you do not have to recompile qt4 with its version of phonon.
  sed -i 9d qtbindings/qtbindings.pro &&

  cd generator      &&
  qmake             &&
  make release      &&
  ./generator $OPTS &&

  cd ../qtbindings  &&
  qmake             &&
  make              &&

  prepare_install   &&
  install ../plugins/script/* /usr/lib/qt4/plugins/script/
