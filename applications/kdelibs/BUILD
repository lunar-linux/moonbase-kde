
  source /etc/profile.d/qt5.rc   &&

  OPTS+=" -DDOCBOOKXML_CURRENTDTD_DIR=/usr/share/sgml/docbook/xml/`lvu version docbook-xml` \
          -DDOCBOOKXSL_DIR=/usr/share/sgml/docbook/xsl-stylesheets-`lvu version docbook-xsl`" &&

  if module_installed taglib ; then
    sedit 's:\(TAGLIB_VERSION STRLESS \"\${TAGLIB_MIN_VERSION}\"\):\(\"\${TAGLIB_MIN_VERSION}\" VERSION_GREATER TAGLIB_VERSION\):g' cmake/modules/FindTaglib.cmake
  fi &&

  if in_depends $MODULE qca2; then
    OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 -DQCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto"
  fi &&

  OPTS+=" -DKDE_DISTRIBUTION_TEXT='Lunar Linux'" &&

  default_cmake_build &&

# If installed use ca-certificates instead of those provided by kdelibs
  if module_installed ca-certificates ; then
    rm -f /usr/share/apps/kssl/ca-bundle.crt &&
    ln -sf /etc/ssl/certs/ca-certificates.crt /usr/share/apps/kssl/ca-bundle.crt
  fi
