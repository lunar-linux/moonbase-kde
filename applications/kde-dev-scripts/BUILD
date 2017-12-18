
  . /etc/profile.d/qt5.rc   &&

# We separate this out on each version bump because
# makeobj is needed at the start of a kde install
  sedit "s:makeobj::" CMakeLists.txt &&

  default_cmake_build
