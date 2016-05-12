
  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  sedit "12i include(CheckIncludeFiles)" CMakeLists.txt &&
  sedit "1i include(CheckIncludeFiles)" ConfigureChecks.cmake &&

  default_cmake_build
