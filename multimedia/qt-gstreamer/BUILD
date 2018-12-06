  . /etc/profile.d/qt5.rc &&

  CXXFLAGS+=" `pkg-config --libs /usr/lib/qt5/pkgconfig/Qt5Core.pc`" &&

  OPTS+=" -DQT_VERSION=5 -DQT_QMAKE_EXECUTABLE=/usr/lib/qt5/bin/qmake -DQTGSTREAMER_EXAMPLES=0" &&

  default_cmake_build
