source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

sed -i 's|SUBDIRS  += Accounts tests|SUBDIRS += Accounts|' accounts-qt.pro &&

/usr/lib/qt6/bin/qmake PREFIX=/usr LIBDIR=/usr/lib $OPTS &&

default_make
