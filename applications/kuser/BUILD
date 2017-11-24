
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

  sedit "38i INCLUDE (CheckIncludeFiles)" CMakeLists.txt &&
  sedit "s:check_include_files:CHECK_INCLUDE_FILES:g" CMakeLists.txt &&

  default_cmake_build
