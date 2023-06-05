source /etc/profile.d/qt6.rc &&

# Temporarily use bundled inid. Stellarium needs to catch up with the indi folks.
OPTS+=" -DCMAKE_CXX_STANDARD=17 -DCMAKE_C_STANDARD=11 -DENABLE_QT6=ON -DPREFER_SYSTEM_INDILIB=OFF"

default_cmake_build
