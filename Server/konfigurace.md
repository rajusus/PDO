
# Konfigurace Serveru

## Základní nastavení

```ini
[server]
host = localhost
port = 8080
environment = development
debug = true
```

## Databáze

```ini
[database]
driver = pdo_mysql
host = localhost
dbname = app_db
user = root
password = 
charset = utf8mb4
```

## Bezpečnost

```ini
[security]
ssl_enabled = true
token_expiry = 3600
max_login_attempts = 5
```

## Logging

```ini
[logging]
level = info
format = json
output = logs/server.log
```
