(

  . /etc/profile.d/qt4.rc &&

  python setup.py build &&

# Fix the depreciated warning about SYSFS and udev.
  sedit "s:SYSFS:ATTR:g" src/calibre/linux.py &&
  sedit "s:BUS:SUBSYSTEM:g" src/calibre/linux.py &&

  prepare_install  &&

  python setup.py install . &&

  sedit "s:Icon=calibre-gui:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-gui.png:" /usr/share/applications/calibre-gui.desktop &&
  sedit "s:Icon=calibre-ebook-edit:Icon=/usr/share/icons/hicolor/256x256/apps/calibre-ebook-edit.png:" /usr/share/applications/calibre-ebook-edit.desktop
) > $C_FIFO 2>&1
