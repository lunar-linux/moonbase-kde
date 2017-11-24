 . /etc/profile.d/qt5.rc &&

 /usr/lib/qt5/bin/qmake kqoauth.pro &&
 default_make &&

# Do the same as we do with qt4/5 to remove referencing the source dir
 sedit "1,2d" /usr/lib/libkqoauth.prl
