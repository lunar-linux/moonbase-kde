source /etc/profile.d/qt5.rc &&

OPTS+=" --confirm-license \
        --no-make \
        --api-dir /usr/share/qt/qsci/api/python \
        --pep484-pyi"

sip-build $OPTS &&

cd build &&
default_make
