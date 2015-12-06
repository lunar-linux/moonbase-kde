 . /etc/profile.d/qt4.rc &&

 sedit 's:TARGET = kqoauth:TARGET = kqoauth-qt4:g' src/src.pro &&
 sedit 's:{INSTALL_PREFIX}/lib:[QT_INSTALL_LIBS]:g' src/src.pro &&
 sedit 's:include/QtKOAuth:include/QtKOAuth-qt4:g' src/src.pro &&
 sedit 's:tests::' kqoauth.pro &&

 sedit 's:QtKOAuth:QtKOAuth-qt4:' src/pcfile.sh &&
 sedit 's:-lkqoauth:-kqoauth-qt4:' src/pcfile.sh &&

 /usr/bin/qmake &&
 default_make
