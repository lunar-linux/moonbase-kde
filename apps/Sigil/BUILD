source /etc/profile.d/qt6.rc &&

#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DUSE_SYSTEM_LIBS=1 -DSYSTEM_LIBS_REQUIRED=1" &&

default_cmake_build
