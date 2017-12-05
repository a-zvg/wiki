#### Работа с SSD

##### Разметка разделов

- `/dev/sda1` - системный для образов ОС;
- `/dev/sda2` - зашифрованный для данных.

##### Форматирование разделов

/dev/sda1:
`mkfs.ext4 -m 0 -O ^has_journal -T largefile4 -E discard,lazy_itable_init=0 /dev/sda1`
`truncate -s 10G os.img`
`losetup /dev/loop7 os.img`
`mkfs.ext4 -m 1 -O ^has_journal -E discard,lazy_itable_init=0 /dev/loop7`

/dev/sda2:
`cryptsetup create work /dev/sda2 -c aes-xts-plain -h sha256 -s 256 --allow-discards`
`mkfs.ext4 -m 0 -E discard,lazy_itable_init=0,lazy_journal_init=0 /dev/mapper/work`

##### Монтирование разделов

/dev/sda1:
`mount /dev/sda1 -o discard,relatime,nodiratime`
`losetup /dev/loop7 os.img`
`mount /dev/loop7 -o discard,relatime,nodiratime`

/dev/sda2
`cryptsetup create work /dev/sda2 -c aes-xts-plain -h sha256 -s 256 --allow-discards`
`mount /dev/mapper/work -o discard,relatime,nodiratime`
