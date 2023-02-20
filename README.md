# Magento 2 - Boilerplate

## Requirements

- Docker
- Den (https://swiftotter.github.io/den/)
## Docker commands

Spin up a new project:
```
den env up
```

Stopping an environment:
```
den env stop
```

Starting a stopped environment:
```
den env start
```

Connecting to the PHP container:
```
den shell
```

## Magento Installation

```
bin/magento setup:install \
--base-url=https://demo.test/ \
--db-host=db \
--db-name=magento \
--db-user=magento \
--db-password=magento \
--admin-firstname=admin \
--admin-lastname=admin \
--admin-email=admin@admin.com \
--admin-user=admin\
--admin-password=admin123 \
--language=fr_FR \
--currency=EUR \
--timezone=Europe/Paris \
--use-rewrites=1 \
--search-engine=elasticsearch7 \
--elasticsearch-host=elasticsearch \
--elasticsearch-port=9200 \
--elasticsearch-index-prefix=magento2 \
--elasticsearch-timeout=15
```

## Redis Configuration

Default Cache
```
bin/magento setup:config:set --cache-backend=redis --cache-backend-redis-server=redis --cache-backend-redis-db=0
```

Page Cache
```
bin/magento setup:config:set --page-cache=redis --page-cache-redis-server=redis --page-cache-redis-db=1

```

Session
```
bin/magento setup:config:set --session-save=redis --session-save-redis-host=redis --session-save-redis-log-level=4 --session-save-redis-db=2
```