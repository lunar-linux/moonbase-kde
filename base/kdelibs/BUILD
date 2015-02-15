
  source /etc/profile.d/qt4.rc   &&

  sed -i "22i /usr/share/sgml/docbook/xml/4.2" cmake/modules/FindDocBookXML.cmake &&

  VER=`lvu version docbook-xsl` &&
  sedit "s:docbook/xsl-stylesheets:docbook/xsl-stylesheets-$VER:" cmake/modules/FindDocBookXSL.cmake &&

  default_cmake_build &&

# If installed use ca-certificates instead of those provided by kdelibs
  if module_installed ca-certificates ; then
    rm -f /usr/share/apps/kssl/ca-bundle.crt &&
    ln -sf /etc/ssl/certs/ca-certificates.crt /usr/share/apps/kssl/ca-bundle.crt
  fi
