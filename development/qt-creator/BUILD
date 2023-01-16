source /etc/profile.d/qt6.rc &&

OPTS+=" -DBUILD_CPLUSPLUS_TOOLS=ON -DBUILD_QBS=OFF"
default_cmake_build &&

# Desktop menu entry
cat > $MODULE.desktop << EOF &&
[Desktop Entry]
Type=Application
Name=Qt6 Creator
Comment=Qt6 based Development Tool
Exec=$QT6_DIR/bin/qtcreator
Icon=/usr/lib/share/icons/hicolor/256x256/apps/QtProject-qtcreator.png
Categories=Development;
EOF

install -D -m644 $MODULE.desktop /usr/share/applications/$MODULE.desktop

# workaround for a runtime bug
#mv /usr/bin/qtcreator /usr/bin/qtcreator-bin &&
#echo "#!/bin/sh" > /usr/bin/qtcreator &&
#echo "QT_LOGGING_TO_CONSOLE=1 qtcreator-bin \$@" >> /usr/bin/qtcreator &&
#chmod +x /usr/bin/qtcreator
