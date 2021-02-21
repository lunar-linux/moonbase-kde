. /etc/profile.d/qt5.rc &&

OPTS+=" --confirm-license \
        --qmake=/usr/lib/qt5/bin/qmake \
        --api-dir /usr/share/sip/PyQt5/Qsci/ " &&

sip-build $OPTS &&

cd build &&
default_make
