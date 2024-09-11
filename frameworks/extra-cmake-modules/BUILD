#disables applications using cmake from attempting to install files in a lib64 sub-directory
sed -i '/"lib64"/s/64//' kde-modules/KDEInstallDirsCommon.cmake &&

#protects the global cmake variable PACKAGE_PREFIX_DIR from being changed when #checking ECM
#presence: since we install ECM into /usr, the check would set that variable to /usr, while
#most KDE packages expect it to be set to /opt/kf5 and would fail to build if it is set to
#something else
sed -e '/PACKAGE_INIT/i set(SAVE_PACKAGE_PREFIX_DIR "${PACKAGE_PREFIX_DIR}")' \
    -e '/^include/a set(PACKAGE_PREFIX_DIR "${SAVE_PACKAGE_PREFIX_DIR}")' \
    -i ECMConfig.cmake.in &&

OPTS+=" -DBUILD_HTML_DOCS=OFF \
        -DBUILD_MAN_DOCS=OFF \
        -DBUILD_QTHELP_DOCS=OFF"

default_cmake_build
