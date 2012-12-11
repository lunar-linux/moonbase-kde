(

# It has trouble finding openjpeg.h
  if in_depends $MODULE openjpeg ; then
    OJ_VER="`lvu version openjpeg | cut -c 1-3`" &&
    CFLAGS+=" -I/usr/include/openjpeg-${OJ_VER}" &&
    LDFLAGS+=" -lopenjpeg" &&
    OPTS+=" -DOPENJPEG_INCLUDE_DIR=/usr/include/openjpeg-${OJ_VER}"
  fi &&

  OPTS+=" -Wno-dev -DWITH_Iconv=ON"   &&


  default_cmake_build

) > $C_FIFO 2>&1
