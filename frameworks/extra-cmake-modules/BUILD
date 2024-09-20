#disables applications using cmake from attempting to install files in a lib64 sub-directory
sed -i '/"lib64"/s/64//' kde-modules/KDEInstallDirsCommon.cmake &&

OPTS+=" -DBUILD_HTML_DOCS=OFF \
        -DBUILD_MAN_DOCS=OFF \
        -DBUILD_QTHELP_DOCS=OFF"

default_cmake_build
