source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

sedit "s:share/xml/docbook/schema/dtd/:/usr/share/sgml/docbook/xml/:" cmake/FindDocBookXML4.cmake &&

OPTS+=" -DBUILD_WITH_QT6=ON"

default_cmake_build
