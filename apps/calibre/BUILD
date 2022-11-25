. /etc/profile.d/qt6.rc &&

# Remove unneeded files
rm resources/mozilla-ca-certs.pem &&
# use system mathjax
rm -rf resources/mathjax &&

LANG='en_US.UTF-8' python setup.py build &&
LANG='en_US.UTF-8' python setup.py gui &&
python setup.py liberation_fonts --path-to-liberation_fonts /usr/share/fonts/liberation-fonts-ttf --system-liberation_fonts
LANG='en_US.UTF-8' python setup.py mathjax --path-to-mathjax /usr/share/mathjax --system-mathjax &&
LANG='en_US.UTF-8' python setup.py rapydscript  &&

prepare_install &&
mkdir -p /usr/share/calibre/system-plugins &&
python setup.py install --root=/usr --prefix=/usr --system-plugins-location=/usr/share/calibre/system-plugins &&

if module_installed zsh; then
   # If this directory doesn't exist, zsh completion won't install.
   install -d /usr/share/zsh/site-functions
fi &&

cp -a man-pages/ /usr/share/man &&
install -Dm644 resources/calibre-mimetypes.xml /usr/share/mime/packages/
