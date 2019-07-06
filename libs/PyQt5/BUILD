. /etc/profile.d/qt5.rc &&

_py_ver=`module_version python`

OPTS+=" --no-timestamp \
        --no-dist-info \
        --sip-incdir=/usr/include/python${_py_ver%.*}m \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake"

if module_installed qscintilla-qt5; then
  OPTS+=" --qsci-api"
fi

python configure.py -w $OPTS &&
default_make
