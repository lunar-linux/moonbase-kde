
  patch_it $SOURCE2 1 &&
  patch_it $SOURCE3 1 &&

  . /etc/profile.d/qt5.rc &&

  sed -i -e '/SUBDIRS += examples/d' Source/QtWebKit.pro &&
  sed -i -e '/CONFIG +=/s/rpath//' \
		Source/WebKit/qt/declarative/{experimental/experimental,public}.pri \
		Tools/qmake/mkspecs/features/{force_static_libs_as_shared,unix/default_post}.prf &&

  /usr/lib/qt5/bin/qmake $OPTS &&

  default_make
