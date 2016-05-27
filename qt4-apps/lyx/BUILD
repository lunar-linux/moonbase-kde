if in_depends $MODULE qt5; then
  . /etc/profile.d/qt5.rc &&
  QTDIR+=" QTDIR=/usr/lib/qt5"
else
  . /etc/profile.d/qt4.rc
fi &&

OPTS+=" --enable-build-type=release" &&

default_build &&

# Desktop menu entry
cat > $MODULE.desktop << EOF &&
[Desktop Entry]
Type=Application
Name=LyX
Comment=The Document Processor
Exec=$QTDIR/bin/lyx
Icon=$QTDIR/share/lyx/images/lyx.png
Categories=Qt;KDE;Graphics;Office;
EOF

install -D -m644 $MODULE.desktop /usr/share/applications/$MODULE.desktop
