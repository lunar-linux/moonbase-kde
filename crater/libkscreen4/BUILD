  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  OPTS+=" -DKDE4_BUILD_TESTS=0" &&

  sedit "s:KSCREEN_TESTS(testscreenconfig )::" tests/CMakeLists.txt &&

  default_cmake_build
