
  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  sedit "6i add_definitions(\${KDE4_ENABLE_EXCEPTIONS})" $MODULE/CMakeLists.txt &&

  default_cmake_build
