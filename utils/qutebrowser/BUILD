export PYTHONHASHSEED=0
make -f misc/Makefile all &&

prepare_install &&

default_python3_build &&

if in_depends asciidoc $MODULE; then
  make -f misc/Makefile PREFIX=/usr &&
  install misc/$MODULE.1 /usr/share/man/man1/
fi &&

for i in 16 24 32 48 64 128 256 512; do
  install -Dm644 icons/qutebrowser-${i}x$i.png /usr/share/icons/hicolor/${i}x$i/apps/qutebrowser.png
done &&

install -Dm644 icons/qutebrowser.svg /usr/share/icons/hicolor/scalable/apps/ &&
install -Dm755 -t /usr/share/qutebrowser/userscripts/ misc/userscripts/*
