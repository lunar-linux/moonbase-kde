source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'


sip-build \
--confirm-license \
    --no-make \
    --qmake=/usr/lib/qt6/bin/qmake6 \
    --pep484-pyi &&

cd build &&
default_make
