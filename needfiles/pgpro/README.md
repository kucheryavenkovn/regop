Используйте инструкции для установки postgreSQL для 1с. Обратите внимание, что команды должны выполняться от пользователя с правами суперпользователя.

```bash
curl -o apt-repo-add.sh https://repo.postgrespro.ru/pg1c-13/keys/apt-repo-add.sh
sh apt-repo-add.sh
```

Если наш продукт единственный Postgres на вашей машине и вы хотите
сразу получить готовую к употреблению базу:

```shell
apt-get install postgrespro-1c-13
```


Если у вас уже установлен другой Postgres и вы хотите чтобы он
продолжал работать параллельно (в том числе и для апгрейда с более
старой major-версии):

```bash
apt-get install postgrespro-1c-13-contrib
/opt/pgpro/1c-13/bin/pg-setup initdb
/opt/pgpro/1c-13/bin/pg-setup service enable
/opt/pgpro/1c-13/bin/pg-setup service start
```