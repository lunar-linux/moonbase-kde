
  . /etc/profile.d/qt5.rc &&

  sedit "54i /usr/share/sgml/docbook/xml/4.5" cmake/FindDocBookXML4.cmake &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1 \
          -DDocBookXSL_DIR=/usr/share/sgml/docbook/xsl-stylesheets-`lvu version docbook-xsl`" &&

  default_cmake_build
