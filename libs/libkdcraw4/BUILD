
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  sedit "24i add_definitions (\$\{KDE4_ENABLE_EXCEPTIONS\})" libkdcraw/CMakeLists.txt &&

  default_cmake_build
