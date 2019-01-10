sedit "s:Icon=cutecom:Icon=/usr/share/cutecom/cutecom.png:" distribution/openSUSE/cutecom.desktop &&
source /etc/profile.d/qt5.rc &&

default_cmake_build &&

mkdir -p /usr/share/icons/cutecom &&
install -D -m 644 ../distribution/openSUSE/cutecom.desktop /usr/share/applications/cutecom.desktop &&
install -D -m 644 ../distribution/cutecom.png /usr/share/icons/cutecom &&
install -D -m 644 ../images/*.svg /usr/share/icons/cutecom &&
install -D -m 644 ../cutecom.1 /usr/share/man/man1/cutecom.1
