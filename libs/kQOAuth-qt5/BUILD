 . /etc/profile.d/qt5.rc &&

 sedit 's:TARGET = kqoauth:TARGET = kqoauth-qt5:g' src/src.pro &&
 sedit 's:{INSTALL_PREFIX}/lib:[QT_INSTALL_LIBS]:g' src/src.pro &&
 sedit 's:include/QtKOAuth:include/QtKOAuth-qt5:g' src/src.pro &&
 sedit 's:tests::' kqoauth.pro &&

 /usr/lib/qt5/bin/qmake &&
 default_make
