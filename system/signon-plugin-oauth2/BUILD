
. /etc/profile.d/qt5.rc &&

# Disalbe warnings as errors
sed -i '/-Werror/d' common-project-config.pri &&

# Do not install tests and example
echo 'INSTALLS =' >>tests/tests.pro     &&
echo 'INSTALLS =' >>example/example.pro &&

/usr/lib/qt5/bin/qmake PREFIX=/usr LIBDIR=/usr/lib $OPTS &&

default_make
