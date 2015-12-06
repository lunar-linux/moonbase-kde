
  patch_it $SOURCE2 3 &&

  . /etc/profile.d/qt4.rc  &&

  sedit "s/^WHICH=.*/WHICH=which/" configure  &&

  ./configure --prefix=${MODULE_PREFIX}  \
              --no-framework             \
              --debug                    \
              --disable-tests            \
              $OPTS                     &&

  default_make
