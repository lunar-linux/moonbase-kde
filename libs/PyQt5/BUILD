. /etc/profile.d/qt5.rc &&

_py_ver=`module_version python`

OPTS+=" --no-timestamp \
        --no-dist-info \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake \
        --sip-incdir=/usr/include/python${_py_ver%.*}m"

if module_installed qscintilla-qt5; then
  OPTS+=" --qsci-api"
fi

python configure.py -w $OPTS &&
default_make
