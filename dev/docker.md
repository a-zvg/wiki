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

Удаление образа:
- `docker rmi <image_id>`

Удаление неиспользуемых образов:
- `docker rmi $(docker images -f "dangling=true" -q) -f`
