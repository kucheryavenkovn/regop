 1. Проверка скорости записи на диск dd if=/dev/zero of=~/testo oflag=direct bs=1M count=4k 
 2. Обновление ядра (на стабильной версии ядра не работал бридж) sudo apt install --install-recommends linux-generic-hwe-20.04
3. Установка сервера по инструкции https://its.1c.ru/db/metod8dev#content:5953:hdoc
4. Установка hasp (указанные в инструкции в п. 3 не работают) дистрибутивы  [здесь](../../needfiles/hasp/)
5. Установка юнита systemd по инструкции https://infostart.ru/public/1341653/
6. Добавление репозитория Postgres curl -o apt-repo-add.sh https://repo.postgrespro.ru/pg1c-13/keys/apt-repo-add.sh
sh apt-repo-add.sh
7. apt-get install postgrespro-1c-13
8. 
