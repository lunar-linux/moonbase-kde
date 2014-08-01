
  source /etc/profile.d/qt4.rc   &&
  source /etc/profile.d/kde4.rc  &&

  sedit "s:PyQt4:PyQt:" sip/phonon/backendcapabilities.sip &&
  sedit "s:typedef://typedef:g" sip/plasma/glapplet.sip &&

  default_cmake_build
