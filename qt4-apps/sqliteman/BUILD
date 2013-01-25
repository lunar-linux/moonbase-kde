(

# A little jiggling of the .desktop so an icon is shown and its devfault placement
# is not in Lost and Found.
  sedit "s:Icon=sqliteman:Icon=/usr/share/sqliteman/icons/sqliteman.png:" sqliteman.desktop &&
  sed -i "11i Categories=Qt;KDE;Development;" sqliteman.desktop &&

  default_cmake_build

) > $C_FIFO 2>&1
