Python
======

Установка
---------

1. Установить python3 из пакета Linux-дистрибутива.
2. Установить pip и venv оттуда же:
  - `apt-get install python3-pip python3-venv --no-install-recommends`
3. Обновить pip и установить setuptools и wheel из PyPI:
  - `python3 -m pip install --user --upgrade pip setuptools wheel`

Полезные команды
----------------

Получить список всех установленных пакетов в системе:
- `python3 -m pip list`

Получить список установленных пакетов из PyPI:
- `python3 -m pip list --user`

Удалить пакет, установленный из PyPI:
- `python3 -m pip uninstall название`

Установка утилиты из PyPI
-------------------------

1. Создать виртуальное окружение:
  - `python3 -m venv ~/название`
2. Активировать виртуальное окружение:
  - `. ~/название/bin/activate`
3. Обновить в виртуальном окружении pip, setuptools и wheel из PyPI:
  - `pip3 install --upgrade pip setuptools wheel`
4. Установить утилиту:
  - `pip3 install название`
5. Создать скрипт запуска утилиты в ~/bin/
```
    #!/bin/bash
    set -e
    . $HOME/название/bin/activate
    $HOME/название/bin/название "$@"
```
