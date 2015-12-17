. /etc/profile.d/qt4.rc &&

sedit "s:add_subdirectory(active)::" CMakeLists.txt &&

# It has trouble finding openjpeg.h because we install the headers in /usr/include/openjpeg-some-version
if in_depends $MODULE openjpeg; then
  sedit "s:/usr/include/openjpeg:/usr/include/openjpeg-`lvu version openjpeg | cut -c 1-3`:" cmake/modules/FindOpenJPEG.cmake
fi &&

if in_depends $MODULE qca2; then
  sedit "s:QtCrypto:Qca-qt4/QtCrypto/QtCrypto:" libs/odf/KoEncryptedStore.h libs/odf/KoEncryptionChecker.cpp filters/libmsooxml/MsooXmlImport.cpp&&
  OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 QCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto"
fi &&

OPTS+=" -DWITH_Iconv=ON -DWITH_GLIB2=1" &&

default_cmake_build
