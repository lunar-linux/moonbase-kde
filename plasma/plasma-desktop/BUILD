
  . /etc/profile.d/qt5.rc &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1  \
          -DKDE_INSTALL_BINDIR=/usr/bin/PlasmaDesktop \
          -DKDE_INSTALL_INCLUDEDIR=/usr/include/KF5  \
          -DKDE_INSTALL_LIBDIR=/usr/lib/KF5          \
          -DKF5SysGuard_DIR=/usr/lib/KF5/cmake/KF5SysGuard     \
          -DKWinDBusInterface_DIR=/usr/lib/KF5/cmake/KWinDBusInterface \
          -DKSMServerDBusInterface_DIR=/usr/lib/KF5/cmake/KSMServerDBusInterface \
          -DKRunnerAppDBusInterface_DIR=/usr/lib/KF5/cmake/KRunnerAppDBusInterface \
          -DLibKWorkspace_DIR=/usr/lib/KF5/cmake/LibKWorkspace \
          -DLibTaskManager_DIR=/usr/lib/KF5/cmake/LibTaskManager" &&
  
  default_cmake_build
