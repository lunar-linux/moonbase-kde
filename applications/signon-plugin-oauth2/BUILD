
  . /etc/profile.d/qt5.rc   &&

  sed -i '/-Werror/d' common-project-config.pri &&

  # We don't need these
  echo 'INSTALLS =' >>tests/tests.pro     &&
  echo 'INSTALLS =' >>example/example.pro &&

  /usr/lib/qt5/bin/qmake PREFIX=/usr LIBDIR=/usr/lib &&
  default_make
