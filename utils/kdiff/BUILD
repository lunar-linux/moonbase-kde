
  source /etc/profile.d/qt5.rc   &&

  sed -i 's@/usr/local@/usr@g' src-QT4/kdiff3.pro src-QT4/kreplacements/kreplacements.cpp &&
  sedit "s:Icon=kdiff3:Icon=/usr/share/icons/kdiff3.ico:" src-QT4/kdiff3.desktop &&
  sedit 's:Exec=kdiff3 %i -caption "%c":Exec=/usr/bin/kdiff3:' src-QT4/kdiff3.desktop &&

  /usr/lib/qt5/bin/qmake src-QT4/kdiff3.pro &&

  default_make &&
  install kdiff3plugin-QT4/kdiff*.desktop /usr/share/applications/ &&
  install src-QT4/kdiff3.desktop /usr/share/applications/ &&
  install src-QT4/kdiff3.ico /usr/share/icons
