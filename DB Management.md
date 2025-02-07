Alle User anzeigen

```SELECT user, host, authentication_string FROM mysql.user;```

Benutzer mit Berechtigungen in einer bestimmten Datenbank

```SELECT user, host FROM mysql.db WHERE db = 'meine_datenbank';```

Neuen Benutzer anlegen

```CREATE USER 'neuer_benutzer'@'localhost' IDENTIFIED BY 'sicheres_passwort'; GRANT ALL PRIVILEGES ON meine_datenbank.* TO 'neuer_benutzer'@'localhost'; FLUSH PRIVILEGES;```

Datenbank für Benutzer via remote Zugriff ermöglichen

```GRANT ALL PRIVILEGES ON DEINEDB.* TO 'USERNAME'@'%' IDENTIFIED BY 'PASSWORT';```


