. /etc/profile.d/qt6.rc  &&

sedit '8i #define GLM_ENABLE_EXPERIMENTAL' ShowMySky/GLWidget.cpp &&
sedit '6i #define GLM_ENABLE_EXPERIMENTAL' common/EclipsedDoubleScatteringPrecomputer.cpp &&

OPTS+=" -DCMAKE_CXX_FLAGS=-fPIC  \
        -DCMAKE_CXX_STANDARD=17 \
        -DCMAKE_CXX_COMPILER=g++ \
        -DQT_VERSION=6"


default_cmake_build
