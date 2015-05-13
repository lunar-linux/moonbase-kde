  source /etc/profile.d/qt5.rc   &&
  source /etc/profile.d/kde4.rc  &&

  sedit "45d" src/backends/R/rserver/rcallbacks.h src/backends/R/rserver/rserver.cpp &&
  sedit "29i #include <Rinterface.h>" src/backends/R/rserver/rcallbacks.cpp &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DPYTHONLIBS3_INCLUDE_DIR=/usr/include/python3.4m \
    -DPYTHON_LIBRARY=/usr/lib/libpython3.so" &&

  default_cmake_build

