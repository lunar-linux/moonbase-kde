
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  sedit "s:set(QJSON_VERSION_REQUIRED 0.7)::" CMakeLists.txt &&
  sed -e "/^cmake_minimum_required/ a cmake_policy(SET CMP0022 OLD)\ncmake_policy(SET CMP0059 OLD)" -i CMakeLists.txt &&
  OPTS+=" -DKDE4_BUILD_TESTS=0" &&

  default_cmake_build
