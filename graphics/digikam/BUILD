
  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&

# https://projects.kde.org/projects/extragear/graphics/digikam/repository/revisions/f6945f23e0ed1e11f26e2c7e62b02baa8cfa640e
  sedit "s:0x020302:0x020400:g" core/libs/imageproperties/captionedit.cpp core/libs/imageproperties/imagedescedittab.cpp &&

# The -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF disables libkipi, 
# libkexiv2 and libkdcraw normally installed by digikam causing
# conflicts with the ones from kde.
  OPTS+=" -Wno-dev -DDIGIKAMSC_USE_PRIVATE_KDEGRAPHICS=OFF" &&

  default_cmake_build
