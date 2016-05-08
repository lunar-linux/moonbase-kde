
  . /etc/profile.d/qt5.rc   &&

# Commenting the first occurance so the adddebug manpage doesn't get created. Causes
# make to fail
  sedit "s:create_manpage:#create_manpage:" doc/CMakeLists.txt &&

# We separate this out on each version bump because
# makeobj is needed at the start of a kde install
  sedit "s:makeobj::" CMakeLists.txt &&

  default_cmake_build
