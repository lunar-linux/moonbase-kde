. /etc/profile.d/qt5.rc &&

sedit 's:gst_caps_append(object<GstCaps>(), gst_caps_copy(caps2));:const GstCaps * caps2ptr = caps2; \gst_caps_append(object<GstCaps>(), gst_caps_copy(caps2ptr));:' src/QGst/caps.cpp &&
sedit 's:GST_PTR_FORMAT: GST_PTR_FORMAT:' elements/gstqtvideosink/delegates/basedelegate.cpp \
                                          elements/gstqtvideosink/delegates/qwidgetvideosinkdelegate.cpp \
                                          elements/gstqtvideosink/gstqtvideosinkbase.cpp &&

OPTS+=" -DQT_VERSION=5 -DQTGSTREAMER_EXAMPLES=0 -DQTGSTREAMER_STATIC=0 -DQTGSTREAMER_CODEGEN=1" &&

default_cmake_build
