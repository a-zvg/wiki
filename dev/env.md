Окружение разработки
====================

1. Установить silversearcher-ag:
  - `sudo apt-get install silversearcher-ag`
2. Установить fzf:
  - скачать собранный артефакт с https://github.com/junegunn/fzf/releases/
  - скопировать бинарь в /usr/local/bin/
3. Установить universal-ctags:
  - скачать архив исходных кодов с https://github.com/universal-ctags/ctags/releases/
  - подготовить инструменты сборки и собрать:
  ```
    sudo apt-get install automake pkg-config --no-install-recommends
    ./autogen.sh
    ./configure
    make -j4
  ```
  - установить в /usr/local/bin/: `sudo make install`
