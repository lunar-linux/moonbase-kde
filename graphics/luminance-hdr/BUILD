
  sedit "31i find_package(Qt5PrintSupport)" CMakeLists.txt &&
  sedit "s:WebKitWidgets:WebKitWidgets PrintSupport:" src/HelpBrowser/CMakeLists.txt &&

  . /etc/profile.d/qt5.rc &&

  default_cmake_build
