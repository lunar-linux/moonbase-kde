(

  OPTS+=" -Wno-dev"   &&

  patch_it $SOURCE2 1 &&
  patch_it $SOURCE3 1 &&

  # fix for glib-2.32
  sedit 's:glib/giochannel.h:glib.h:' filters/kword/msword-odf/wv2/src/olestream.h &&

  default_cmake_build

) > $C_FIFO 2>&1
