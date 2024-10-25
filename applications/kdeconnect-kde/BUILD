source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

#kdeconnects mdns will conflict with that used by avahi
if module_installed nss-mdns; then
  OPTS+=" -DMDNS_ENABLED=OFF"
fi &&

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON"

default_cmake_build
