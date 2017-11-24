

  . /etc/profile.d/qt5.rc   &&

  OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=1" &&

  sedit "47i IconThemes" CMakeLists.txt &&

  default_cmake_build &&

# With X-DBUS-StartupType=Multi kinit gets confused so we just set to none.
# Multiple files can still be opened within Kate, just eliminates the error popup.
  sedit "s:X-DBUS-StartupType=Multi:X-DBUS-StartupType=None:" /usr/share/applications/org.kde.kate.desktop
