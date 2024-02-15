. /etc/profile.d/qt5.rc &&

OPTS+=" -DBUILD_SHARED_LIBS=ON"

default_cmake_build

mkdir -p /usr/lib/cmake/kImageAnnotator &&
ln -sr /usr/lib/cmake/kImageAnnotator-Qt5/kImageAnnotator-Qt5Config.cmake /usr/lib/cmake/kImageAnnotator/kImageAnnotatorConfig.cmake &&
ln -sr /usr/lib/cmake/kImageAnnotator-Qt5/kImageAnnotator-Qt5Config-version.cmake /usr/lib/cmake/kImageAnnotator/kImageAnnotatorConfig-version.cmake &&
ln -sr /usr/lib/cmake/kImageAnnotator-Qt5/kImageAnnotator-targets* /usr/lib/cmake/kImageAnnotator/
