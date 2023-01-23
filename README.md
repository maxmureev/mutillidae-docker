# OWASP Mutillidae II in Docker

Форкнул [тут](https://github.com/webpwnized/mutillidae-docker), починил и оптимизировал. Сделано для сборки под ARM64

## Запуск

Если Кали, поставить зависимость, если мак, то уже поставилось с Докером
```
sudo apt install docker-compose
```

Скачать файл конфигурации
```
wget https://raw.githubusercontent.com/maxmureev/mutillidae-docker/master/docker-compose.yml -O ~/docker-compose.yml
```

Запустить
```
docker-compose -f ~/docker-compose.yml up -d
```

В браузере перейти по http://localhost/set-up-database.php для заполнения БД.
Затем в http://localhost

Остановить
```
docker-compose -f ~/docker-compose.yml down
```


## Порты
- Port 80: OWASP Mutillidae II (HTTP web interface)
- Port 81: phpMyAdmin (MySQL Admin HTTP web interface)
- Port 82: LDAP Admin web interface
- Port 389: LDAP interface


## Другое
В файле mutillidae.ldif есть данные которыми можно заполнить LDAP, сделать можно так:
```
ldapadd -c -x -D "cn=admin,dc=mutillidae,dc=localhost" -w mutillidae -H ldap:// -f mutillidae.ldif
```
