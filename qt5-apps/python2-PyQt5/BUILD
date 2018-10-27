. /etc/profile.d/qt5.rc &&

OPTS+=" --no-timestamp \
        --no-dist-info \
        --sip-incdir=/usr/include/python2.7 \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake"

if module_installed qscintilla2; then
  OPTS+=" --qsci-api"
fi &&

python2 configure.py $OPTS &&
default_make
