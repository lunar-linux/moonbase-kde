
. /etc/profile.d/qt5.rc &&

default_cmake_build &&

#Baloo liks a large max-user-watches greater than 8192
#Instead of fiddling with the 99-sysctl.conf, we will
#just make a new file just for that.

echo fs.inotify.max_user_watches=524288 > /etc/sysctl.d/40-max-user-watches.conf
