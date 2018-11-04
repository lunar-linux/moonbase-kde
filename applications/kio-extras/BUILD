if in_depends $MODULE openexr ;then
  VER+=`lvu version openexr|cut -d. -f1-2 | sed 's/\./_/g'`
  OPTS+=" -DOpenEXR_HALF_LIBRARY=/usr/lib/libHalf-2_3.so  \
          -DOpenEXR_IEX_LIBRARY=/usr/lib/libIex-2_3.so    \
          -DOpenEXR_ILMIMF_LIBRARY=/usr/lib/libIlmImf-2_3.so \
          -DOpenEXR_ILMTHREAD_LIBRARY=/usr/lib/libIlmThread-2_3.so \
          -DOpenEXR_IMATH_LIBRARY=/usr/lib/libImath-2_3.so"
fi &&

. /etc/profile.d/qt5.rc &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

default_cmake_build
