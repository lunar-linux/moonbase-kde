source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

sip-build \
    --confirm-license \
    --qmake=/usr/lib/qt6/bin/qmake \
    --api-dir /usr/share/qt6/qsci/api/python \
    --pep484-pyi &&

cd build &&
default_make
