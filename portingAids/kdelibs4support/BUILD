
  . /etc/profile.d/qt5.rc &&

  sedit "s:share/xml/docbook/schema/dtd/:/usr/share/sgml/docbook/xml/:" cmake/FindDocBookXML4.cmake &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  default_cmake_build
