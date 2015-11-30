
  source /etc/profile.d/qt4.rc   &&

  OPTS+=" -DDOCBOOKXML_CURRENTDTD_DIR=/usr/share/sgml/docbook/xml/`lvu version docbook-xml` \
          -DDOCBOOKXSL_DIR=/usr/share/sgml/docbook/xsl-stylesheets-`lvu version docbook-xsl`" &&

  if module_installed taglib ; then
    sedit 's:\(TAGLIB_VERSION STRLESS \"\${TAGLIB_MIN_VERSION}\"\):\(\"\${TAGLIB_MIN_VERSION}\" VERSION_GREATER TAGLIB_VERSION\):g' cmake/modules/FindTaglib.cmake
  fi &&

  default_cmake_build &&

# If installed use ca-certificates instead of those provided by kdelibs
  if module_installed ca-certificates ; then
    rm -f /usr/share/apps/kssl/ca-bundle.crt &&
    ln -sf /etc/ssl/certs/ca-certificates.crt /usr/share/apps/kssl/ca-bundle.crt
  fi
