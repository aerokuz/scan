### Заметки и инструкции к проекту scan.aerokuz.ru
1. Для автоматического запуска docker-compose необходимо файл **docker-compose-app.service** переместить в */etc/systemd/system/* после чего вбить комманду в терминале **systemctl enable docker-compose-app**

### Backup и Restore

# 1. Backup-  Переходим в папку куда хотим положить backup и выполняем команду
	docker exec ID_CONTAINER /usr/bin/mysqldump -u root --password=rootpass --routines --events  NAME_DATABASE > NAME_BACKUP_FILE
# 2. Restore- Переходим в папку c файлом backup и выполняем команду
	cat NAME_BACKUP_FILE | sudo docker exec -i ID_CONTAINER /usr/bin/mysql -u root --password=rootpass NAME_DATABASE

### Описание файлов и папок
1. **/etc/mysql/my.cnf**- файл конфигурации mysql
2. **/hosts**- файлы конфигурации nginx
3. **/images**- используемые образы docker контейнеров

> **/images/php**- файлы docker и настройка php

4. **/logs/nginx**- сюда падают логи из docker контейнера nginx
5. **/www**- настройка php внутри docker контейнера
6. **docker-compose.yml**- файл конфигурации docker-compose
