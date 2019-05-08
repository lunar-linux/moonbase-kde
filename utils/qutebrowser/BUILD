prepare_install &&

default_python3_build &&

for i in 16 24 32 48 64 128 256 512; do
  install -Dm644 icons/qutebrowser-${i}x$i.png /usr/share/icons/hicolor/${i}x$i/apps/qutebrowser.png
done &&

install -Dm644 icons/qutebrowser.svg /usr/share/icons/hicolor/scalable/apps/ &&
install -Dm755 -t /usr/share/qutebrowser/userscripts/ misc/userscripts/*
