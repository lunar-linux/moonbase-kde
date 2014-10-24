
  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&


# The -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF disables libkipi, 
# libkexiv2 and libkdcraw normally installed by digikam causing
# conflicts with the ones from kde.
  OPTS+=" -Wno-dev -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF -DWITH_ImageMagick=OFF" &&

  default_cmake_build
