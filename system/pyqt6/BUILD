source /etc/profile.d/qt6.rc &&

sip-build \
    --confirm-license \
    --no-make \
    --qmake=/usr/lib/qt6/bin/qmake \
    --api-dir /usr/share/qt6/qsci/api/python \
    --pep484-pyi &&

cd build &&
default_make
