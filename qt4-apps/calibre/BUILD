  . /etc/profile.d/qt5.rc &&

  python setup.py build &&

  prepare_install  &&

  python setup.py install . &&

  sedit "s:Icon=calibre-gui:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-gui.png:" /usr/share/applications/calibre-gui.desktop &&
  sedit "s:Icon=calibre-ebook-edit:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-ebook-edit.png:" /usr/share/applications/calibre-ebook-edit.desktop
