
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1                  \
          -DKDE_INSTALL_INCLUDEDIR=/usr/include/KF5         \
          -DKDE_INSTALL_LIBDIR=/usr/lib/KF5                 \
          -DKDE_INSTALL_BINDIR=/usr/bin/$MODULE             \
          -DKWinDBusInterface_DIR=/usr/lib/KF5/cmake/KWinDBusInterface \
          -DKF5SysGuard_DIR=/usr/lib/KF5/cmake/KF5SysGuard" &&

  default_cmake_build
