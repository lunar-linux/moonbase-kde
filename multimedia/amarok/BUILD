(

  patch_it $SOURCE2 0 &&

  find . -type f -print0 | xargs -0 sed -i \
  -e 's/AMAROK_SQLCOLLECTION_EXPORT_TESTS/AMAROK_SQLCOLLECTION_EXPORT/g' \
  -e 's/AMAROK_EXPORT_TESTS/AMAROK_EXPORT/g' &&

  sedit "11i add_definitions(-DMAKE_AMAROK_TESTS)" tests/CMakeLists.txt &&

  source /etc/profile.d/qt4.rc &&

  default_cmake_build

) > $C_FIFO 2>&1
