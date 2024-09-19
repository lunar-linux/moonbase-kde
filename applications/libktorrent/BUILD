# Gentoo workaround because gmp.h in MULTILIB_WRAPPED_HEADERS is breaking this
sed -i -e "/^find_package/ s/\"\${LibGMP_MIN_VERSION}\" //" CMakeLists.txt &&
sed -i -e "/^find_dependency/ s/ \"@LibGMP_MIN_VERSION@\"//" KTorrent6Config.cmake.in &&

source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

OPTS+=" -DKDE_INSTALL_USE_QT_SYS_PATHS=ON -DWITH_XFS=OFF"

default_cmake_build
