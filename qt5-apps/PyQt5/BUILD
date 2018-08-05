. /etc/profile.d/qt5.rc &&

# For qt5-5.10.0 support
sedit "s:Qt_5_9_3}:Qt_5_9_3 Qt_5_10_0 Qt_5_10_1}:" sip/QtCore/QtCoremod.sip &&

OPTS+=" --no-timestamp \
        --no-sip-files \
        --no-dist-info \
        --assume-shared \
        --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake"

if module_installed qscintilla-qt5; then
  OPTS+=" --qsci-api"
fi &&

python configure.py -w $OPTS &&
default_make
