(

  patch_it $SOURCE2 1 &&

# A gcc twiddle.
  sed -i "29i #include <unistd.h>" strigidaemon/bin/daemon/eventlistener/eventlistenerqueue.cpp &&

# So nepomukindexer stops segfaulting on ffmpeg libavformat.so. Taken from kde support strigi
# commit bb733a4f.
  sedit 's:indexing FFMPEG\"):indexing FFMPEG\" COMPONENTS AVCODEC AVFORMAT AVUTIL SWSCALE ):' libstreamanalyzer/CMakeLists.txt &&

# Sqlite and inotify are unreliabe, so making them a hard off.
  OPTS+=" -DENABLE_SQLITE=OFF -DENABLE_INOTIFY=OFF" &&

  default_cmake_build

) > $C_FIFO 2>&1
