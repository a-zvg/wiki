Conan
=====

Установка
---------

1. Создать виртуальное окружение:
  - `python3 -m venv ~/conan`
2. Активировать виртуальное окружение conan:
  - `. ~/conan/bin/activate`
3. Обновить pip, setuptools и wheel из PyPI:
  - `pip3 install --upgrade pip setuptools wheel`
4. Установить conan:
  - `pip3 install conan`
5. Создать скрипт запуска conan в ~/bin/conan
```
    #!/bin/bash
    set -e
    . $HOME/conan/bin/activate
    $HOME/conan/bin/conan $@
```

Настройка
---------

В ~/.conan/profiles/default установить использование нового ABI C++11:
  - `conan profile new default --detect`
  - `conan profile update settings.compiler.libcxx=libstdc++11 default`

Полезные команды
----------------

Отобразить текущие загруженные библиотеки:
  - `conan search`

Поиск библиотеки:
  - `conan search <название> -r conan-center`

Удилить библиотеку:
  - `conan remove <название>`
