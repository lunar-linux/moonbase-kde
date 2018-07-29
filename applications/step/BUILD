  source /etc/profile.d/qt5.rc   &&

  sed -e '/find_package.*Xml Test/ s/^/#/' -i stepcore/CMakeLists.txt &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 -DBUILD_doc=OFF -DBUILD_po=OFF" &&

  default_cmake_build
