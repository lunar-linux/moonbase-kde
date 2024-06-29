source /etc/profile.d/qt6.rc &&
export LANG='en_US.UTF-8'

mkdir -p $MODULE-$VERSION &&
cd $MODULE-$VERSION &&
qmake6 ../$MODULE.pro PREFIX=/usr &&
default_make
