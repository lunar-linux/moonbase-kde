
  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&

# The -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF disables libkipi, 
# libkexiv2 and libkdcraw normally installed by digikam causing
# conflicts with the ones from kde.
  OPTS+=" -Wno-dev -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF -DWITH_ImageMagick=OFF" &&

# To avoid a conflict
  if module_installed libksane ; then
    OPTS+=" -DWITH_KSane=OFF"
   else OPTS+=" -DWITH_KSane=ON"
  fi &&

  default_cmake_build
