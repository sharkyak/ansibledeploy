## Requirements

    ansible-galaxy collection install community.aws

В файле full.yml в переменной keypair прописать имя ssh key

## Запуск

    ansible-playbook full.yml

Машина с которой запускается плейбук должна находиться в одной локальной сети с запускаемыми инстансами поскольку подключение идет по private ip

## Поведение

1. Если ничего не менять в instances.yml - ничего не меняет - можно запускать сколько угодно раз
2. При добавлении записи в instances.yml - запускает соответсвующие новые инстансы
3. При удалении записи из instances.yml - останавливает соответсвующие запущенные инстансы
4. В случае запуска новых инстансев\остановки запущенных перезаписывает nginx конфиг на web инстансах
5. Каждый запущенный инстанс тегируется Name состоящим из имени и номера и Role - соответсвующей ролью web или app