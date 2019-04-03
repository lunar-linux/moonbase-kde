. /etc/profile.d/qt5.rc &&

OPTS+=" --no-timestamp \
        --no-dist-info \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake"

if module_installed qscintilla-qt5; then
  OPTS+=" --qsci-api"
fi

python configure.py -w $OPTS &&
default_make
