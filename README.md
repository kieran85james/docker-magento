### Docker compose config for Magento2

- `WEB_ALIAS_DOMAIN` is the local domain you are using. This
must be set in your `/etc/hosts` file.
- If you wish to use XDebug with VScode then you must
add path mappings to your `launch.json`. Example:
```
. . .
     "pathMappings": {
          "/app": "${workspaceFolder}"
      },
. . .
```
- To import a `*.sql` file in to the mysql database use
the following command: `docker exec -i {container_name} mysql -u{user} -p{password} {database} < {path_to_sql_file}.sql`
- Install grunt using: `curl -sL https://deb.nodesource.com/setup_16.x | bash - && apt-get install -y nodejs && npm install npm install -g grunt-cli && npm update

### Installing Magento
See: https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/composer.html

1. `composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition <install-directory-name>
`
2. `bin/magento setup:install --base-url=https://magento.local --db-host=mysql --db-name=magento --db-user=root --db-password=root --admin-firstname=FIRSTNAME --admin-lastname=LASTNAME --admin-email=EMAIL --admin-user=NAME --admin-password=PASSWORD --language=en_GB --currency=GBP --timezone=Europe/London --use-rewrites=1 --opensearch-host=opensearch --opensearch-port=9200 --opensearch-index-prefix=dm`
