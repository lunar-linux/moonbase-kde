. /etc/profile.d/qt5.rc &&

mkdir -p build-$MODULE &&
cd build-$MODULE &&

CXXFLAGS+=" -I/usr/include/ffmpeg4/" \
LDFLAGS+=" `pkgconf --libs /usr/lib/ffmpeg4/pkgconfig/*.pc`" \
CFLAGS+=" -I/usr/include/ffmpeg4/" \
qmake-qt5 ../QtAV.pro "CONFIG += no-examples" \
QMAKE_CXXFLAGS="$CXXFLAGS -I/usr/include/ffmpeg4/" \
QMAKE_LFLAGS="$LDFLAGS `pkgconf --libs /usr/lib/ffmpeg4/pkgconfig/*.pc`" &&
QMAKE_CFLAGS="$CFLAGS -I/usr/include/ffmpeg4/" \

#LIBS="$LIBS -L/usr/lib/ffmpeg4/ -lavcodec -lavdevice -lavfilter -lavformat -lavutil -lpostproc -lswresample -lswscale" &&
#LIBS+=" -L/usr/lib/ffmpeg4/ -lavcodec -lavdevice -lavfilter -lavformat -lavutil -lpostproc -lswresample -lswscale" \

default_make
