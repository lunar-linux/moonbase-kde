. /etc/profile.d/qt5.rc &&

rm resources/mozilla-ca-certs.pem &&
rm -rf resources/mathjax &&

LANG='en_US.UTF-8' CALIBRE_PY3_PORT=1 python setup.py build &&
LANG='en_US.UTF-8' CALIBRE_PY3_PORT=1 python setup.py gui &&
LANG='en_US.UTF-8' CALIBRE_PY3_PORT=1 python setup.py mathjax --path-to-mathjax /usr/share/mathjax --system-mathjax &&
#LANG='en_US.UTF-8' CALIBRE_PY3_PORT=1 python setup.py rapydscript &&

prepare_install &&

XDG_DATA_DIRS=/usr/share \
      LANG='en_US.UTF-8' \
      CALIBRE_PY3_PORT=1 python setup.py install --staging-root=/usr --prefix=/usr &&

cp -a man-pages/ /usr/share/man &&
install -Dm644 resources/calibre-mimetypes.xml /usr/share/mime/packages/
