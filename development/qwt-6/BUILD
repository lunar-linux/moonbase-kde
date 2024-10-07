source /etc/profile.d/qt5.rc &&

sedit 's:/usr/local/qwt-$$QWT_VERSION:/usr:g' qwtconfig.pri &&
sedit 's:/doc:/share/doc:' qwtconfig.pri &&
sedit 's:include:include/qwt:' qwtconfig.pri &&
sedit 's:plugins/designer:lib/qt5/plugins/designer:g' qwtconfig.pri &&

/usr/lib/qt5/bin/qmake &&
default_make
