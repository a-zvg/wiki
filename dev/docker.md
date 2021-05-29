Docker и Docker Compose
=======================

Установка
---------

TODO

Полезные команды
----------------

Список образов:
- `docker images`

Загрузка образа из Docker Hub:
- `docker pull <имя_образа>`

Запуск контейнера из образа в интерактивном режиме с содержимым текущей папки:
- `docker run -v $PWD:/opt/app -w /opt/app -it osll/mooc_linux_programming /bin/bash`

Удаление образа:
- `docker rmi <image_id>`

Удаление неиспользуемых образов:
- `docker rmi $(docker images -f "dangling=true" -q) -f`
