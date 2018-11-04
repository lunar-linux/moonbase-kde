if in_depends $MODULE openexr ;then
  VER+=`lvu version openexr|cut -d. -f1-2 | sed 's/\./_/g'`
  OPTS+=" -DOpenEXR_HALF_LIBRARY=/usr/lib/libHalf-${VER}.so  \
          -DOpenEXR_IEX_LIBRARY=/usr/lib/libIex-${VER}.so    \
          -DOpenEXR_ILMIMF_LIBRARY=/usr/lib/libIlmImf-${VER}.so \
          -DOpenEXR_ILMTHREAD_LIBRARY=/usr/lib/libIlmThread-${VER}.so \
          -DOpenEXR_IMATH_LIBRARY=/usr/lib/libImath-${VER}.so"
fi &&

. /etc/profile.d/qt5.rc &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

default_cmake_build
