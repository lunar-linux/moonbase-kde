. /etc/profile.d/qt5.rc &&

LANG='en_US.UTF-8' python2 setup.py build &&
LANG='en_US.UTF-8' python2 setup.py gui &&

prepare_install  &&

python2 setup.py install . &&

sedit "s:Icon=calibre-gui:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-gui.png:" /usr/share/applications/calibre-gui.desktop &&
sedit "s:Icon=calibre-ebook-edit:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-ebook-edit.png:" /usr/share/applications/calibre-ebook-edit.desktop
