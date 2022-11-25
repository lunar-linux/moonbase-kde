source /etc/profile.d/qt6.rc &&

OPTS+=" --confirm-license \
        --no-make \
        --qmake=/usr/lib/qt6/bin/qmake6 \
        --pep484-pyi \
        --api-dir /usr/share/qt/qsci/api/python"

sip-build $OPTS &&

cd build &&
default_make
