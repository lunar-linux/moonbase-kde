. /etc/profile.d/qt5.rc &&

rm -rf resources/$MODULE-portable.* &&

LANG='en_US.UTF-8' python2 setup.py build &&
LANG='en_US.UTF-8' python2 setup.py gui &&
LANG='en_US.UTF-8' python2 setup.py mathjax &&

prepare_install &&

XDG_DATA_DIRS=/usr/share \
      LANG='en_US.UTF-8' \
      python2 setup.py install --root=/usr --prefix=/usr &&

cp -a man-pages/ /usr/share/man &&
install -Dm644 resources/calibre-mimetypes.xml /usr/share/mime/packages/
