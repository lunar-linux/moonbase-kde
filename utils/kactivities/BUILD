
  . /etc/profile.d/qt4.rc   &&
  . /etc/profile.d/kde4.rc  &&

# nepomuk is going by the wayside. Enabling libraries only, this will prevent the installation of 
# /usr/bin/kactivitymanagerd which conflicts with kactivitymanagerd (applications).
  OPTS+=" -DWITH_NepomukCore=0 -DKACTIVITIES_LIBRARY_ONLY=1" &&

  default_cmake_build
