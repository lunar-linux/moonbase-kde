
  source /etc/profile.d/qt5.rc &&

  sed -i "34i /usr/share/sgml/docbook/xml/4.5" cmake/FindDocBookXML4.cmake &&

  VER=`lvu version docbook-xsl` &&
  sedit "s:docbook/xsl-stylesheets:docbook/xsl-stylesheets-$VER:" cmake/FindDocBookXSL.cmake &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  default_cmake_build
