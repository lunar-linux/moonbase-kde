
  source /etc/profile.d/qt4.rc  &&
  source /etc/profile.d/kde4.rc &&

# Disabling these here else the digikam provided ones will conflict
# with the ones from kde. We will use the digikam provided libkface.
  OPTS+=" -Wno-dev  -DDIGIKAMSC_COMPILE_LIBKDCRAW=0 \
                    -DDIGIKAMSC_COMPILE_LIBKEXIV2=0 \
                    -DDIGIKAMSC_COMPILE_LIBKFACE=1  \
                    -DDIGIKAMSC_COMPILE_LIBKIPI=0   \
                    -DDIGIKAMSC_COMPILE_LIBKSANE=0" &&

  default_cmake_build
