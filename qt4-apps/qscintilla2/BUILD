
# install the editor class

  export PATH=$QTDIR/bin:$PATH  &&
  source /etc/profile.d/qt4.rc  &&
  cd Qt4Qt5                     &&

  qmake -o Makefile qscintilla.pro &&
  default_make  &&

  
# install the Python bindings

  cd ../Python           &&
  python ./configure.py  &&
  default_make

# Do Python-3
  if in_depends $MODULE Python-3 ; then
    devoke_installwatch &&
    python3 ./configure.py &&
    default_make
  fi
