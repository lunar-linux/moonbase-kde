source /etc/profile.d/qt6.rc &&

sedit 's:/usr/local/qwt-$$QWT_VERSION:/usr:g' qwtconfig.pri &&
sedit 's:/doc:/share/doc:' qwtconfig.pri &&
sedit 's:include:include/qwt:' qwtconfig.pri &&
sedit 's:plugins/designer:lib/qt6/plugins/designer:g' qwtconfig.pri &&

/usr/lib/qt6/bin/qmake &&
default_make
