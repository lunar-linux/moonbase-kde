

  source /etc/profile.d/qt5.rc   &&
  source /etc/profile.d/kde4.rc  &&

  default_cmake_build &&

# With X-DBUS-StartupType=Multi kinit gets confused so we just set to none.
# Multiple files can still be opened within Kate, just eliminates the error popup.
  sedit "s:X-DBUS-StartupType=Multi:X-DBUS-StartupType=None:" /usr/share/applications/org.kde.kate.desktop
