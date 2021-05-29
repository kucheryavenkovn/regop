# Настройка резервного копирования баз 1С

Создал скрипт, создающий дампы баз данных
```bash
#/bin/bash
export PGPASSWORD=secret1c
pg_dump -h 127.0.0.1 -U postgres --format custom -b --section pre-data --section data --section post-data --verbose --file /backup/ro/ro-$(date +%Y-%m-%d).bkp ro
pg_dump -h 127.0.0.1 -U postgres --format custom -b --section pre-data --section data --section post-data --verbose --file /backup/do/do-$(date +%Y-%m-%d).bkp do
```

для того, чтобы при запуске скрипта pg_dump не запрашивал пароль создал файл /root/.pgpass со следующим содержимым:

```
127.0.0.1:5432:ro:postgres:secret1c
127.0.0.1:5432:do:postgres:secret1c
```

Добавил его запуск в сcrontab

```
0 9 * * * /etc/backup_pg_bases.sh
```
