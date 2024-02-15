OPTS+=" -DBUILD_SHARED_LIBS=ON"

default_cmake_build &&

mkdir -p "$pkgdir"/usr/lib/cmake/kColorPicker &&

ln -sr /usr/lib/cmake/kColorPicker-Qt5/kColorPicker-Qt5Config.cmake /usr/lib/cmake/kColorPicker/kColorPickerConfig.cmake &&
ln -sr /usr/lib/cmake/kColorPicker-Qt5/kColorPicker-Qt5Config-version.cmake /usr/lib/cmake/kColorPicker/kColorPickerConfig-version.cmake &&
ln -sr /usr/lib/cmake/kColorPicker-Qt5/kColorPicker-Qt5-targets* /usr/lib/cmake/kColorPicker/
