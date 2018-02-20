
  source /etc/profile.d/qt5.rc   &&

# Do not change these, prevents conflicts with kholidays-frameworks
  OPTS+="  -DKDE_INSTALL_USE_QT_SYS_PATHS=1             \
           -DKDE_INSTALL_LIBDIR=lib/kholidays-applications  \
           -DKDE_INSTALL_QMLDIR=lib/kholidays-applications \
           -DECM_MKSPECS_INSTALL_DIR=mkspecs/modules/kholidays-applications \
           -DKDE_INSTALL_INCLUDEDIR=include/KHolidays-applications" &&

  default_cmake_build
