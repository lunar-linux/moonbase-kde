
  . /etc/profile.d/qt5.rc &&

  sed -i 's|lib64|lib|' src/src.pro %%
  /usr/lib/qt5/bin/qmake qoauth.pro &&

  default_make
