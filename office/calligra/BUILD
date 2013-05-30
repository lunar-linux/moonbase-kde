
# It has trouble finding openjpeg.h because we install the headers in /usr/include/openjpeg-some-version
  if in_depends $MODULE openjpeg ; then
    sedit "s:/usr/include/openjpeg:/usr/include/openjpeg-`lvu version openjpeg | cut -c 1-3`:" cmake/modules/FindOpenJPEG.cmake
  fi &&

  OPTS+=" -Wno-dev -DWITH_Iconv=ON" &&

  default_cmake_build
