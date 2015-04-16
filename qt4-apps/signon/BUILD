
 . /etc/profile.d/qt4.rc &&

 qmake PREFIX=/usr $OPTS &&
 default_make &&

 if in_depends $MODULE qt5 ; then
   . /etc/profile.d/qt5.rc &&
   /usr/lib/qt5/bin/qmake PREFIX=/usr$OPTS &&
   default_make
 fi

