
  . /etc/profile.d/qt4.rc &&
  . /etc/profile.d/kde4.rc &&

  sedit "s:QtCrypto:Qca-qt4/QtCrypto/QtCrypto:" protocols/jabber/libiris/src/xmpp/xmpp-core/xmpp_clientstream.h \
                                                protocols/jabber/libiris/src/xmpp/xmpp-core/xmpp.h \
                                                protocols/jabber/libiris/src/irisnet/noncore/cutestuff/httppoll.cpp \
                                                protocols/jabber/libiris/src/irisnet/noncore/cutestuff/httpconnect.cpp \
                                                protocols/jabber/libiris/src/xmpp/xmpp-im/xmpp_vcard.cpp \
                                                protocols/jabber/libiris/src/xmpp/xmpp-im/xmpp_ibb.cpp \
                                                protocols/jabber/libiris/src/xmpp/sasl/digestmd5response.cpp \
                                                protocols/jabber/libiris/src/xmpp/sasl/scramsha1message.cpp \
                                                protocols/jabber/libiris/src/xmpp/sasl/scramsha1signature.h \
                                                protocols/jabber/libiris/src/xmpp/sasl/scramsha1signature.cpp \
                                                protocols/jabber/libiris/src/xmpp/sasl/scramsha1response.h \
                                                protocols/jabber/libiris/src/xmpp/sasl/scramsha1response.cpp \
                                                protocols/jabber/libiris/src/xmpp/xmpp-core/tlshandler.cpp \
                                                protocols/jabber/libiris/src/xmpp/xmpp-core/stream.cpp &&

  sedit "s:qca.h:Qca-qt4/QtCrypto/qca.h:" protocols/jabber/libiris/src/xmpp/xmpp-core/securestream.h \
                                          protocols/jabber/libiris/src/xmpp/xmpp-im/s5b.cpp \
                                          protocols/jabber/libiris/src/xmpp/xmpp-core/tlshandler.cpp &&
  OPTS+=" -DQCA2_LIBRARIES=/usr/lib/libqca-qt4.so.2 QCA2_INCLUDE_DIR=/usr/include/Qca-qt4/QtCrypto" &&

# Prefer it look here instead of /usr/lib/mozilla/plugins
  OPTS+=" -DMOZPLUGIN_INSTALL_DIR=/usr/lib/lunar/plugins" &&
  default_cmake_build
