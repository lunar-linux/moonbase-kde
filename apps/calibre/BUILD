source /etc/profile.d/qt6.rc &&
export PYTHONDONTWRITEBYTECODE=1 &&
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

rm resources/calibre-portable.* &&
mkdir -p manual/locale &&
mkdir -p resources/localization/locales &&
mkdir -p translations/manual &&

python setup.py build &&
python setup.py iso639 &&
python setup.py iso3166 &&
python setup.py translations &&
python setup.py liberation_fonts --system-liberation_fonts --path-to-liberation_fonts /usr/share/fonts/liberation-fonts-ttf &&
#python setup.py mathjax --system-mathjax --path-to-mathjax /usr/share/mathjax &&
python setup.py gui &&
python setup.py resources &&

prepare_install &&
mkdir -p /usr/share/calibre/system-plugins &&
python setup.py install --root=/usr --prefix=/usr --system-plugins-location=/usr/share/calibre/system-plugins &&

if module_installed zsh; then
   # If this directory doesn't exist, zsh completion won't install.
   install -d /usr/share/zsh/site-functions
fi &&

install -Dm644 resources/calibre-mimetypes.xml /usr/share/mime/packages/
