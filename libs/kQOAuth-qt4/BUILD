 . /etc/profile.d/qt4.rc &&

 sedit 's:TARGET = kqoauth:TARGET = kqoauth-qt4:g' src/src.pro &&
 sedit 's:{INSTALL_PREFIX}/lib:[QT_INSTALL_LIBS]:g' src/src.pro &&
 sedit 's:include/QtKOAuth:include/QtKOAuth-qt4:g' src/src.pro &&
 sedit 's:tests::' kqoauth.pro &&

 /usr/bin/qmake &&
 default_make
