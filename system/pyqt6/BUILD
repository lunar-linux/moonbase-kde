source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

CXXFLAGS+=" -std=c++17" \
    sip-build \
    --confirm-license \
    --no-make \
    --qmake=/usr/lib/qt6/bin/qmake6 \
    --confirm-license \
    --api-dir /usr/share/qt6/qsci/api/python \
    --pep484-pyi &&

cd build &&
default_make
