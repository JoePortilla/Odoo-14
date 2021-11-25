# Usage
Cambie el permiso de la carpeta para asegurarse de que el contenedor puede acceder al directorio:

```
$ sudo chmod -R 777 addons
$ sudo chmod -R 777 etc
```

Poner en marcha el contenedor:
```
$ docker-compose up
```

* Entonces abre `localhost:8071` para acceder a Odoo 14.0. Si desea iniciar el servidor con un puerto diferente, cambie **ODOO_PORT** en .env por otro valor:

```
ports:
 - "8071:8069"
```


* El archivo de registro se imprime en **etc/odoo-server.log**

Para ejecutar en modo independiente, ejecute este comando:

```
$ docker-compose up -d
```

# Custom addons

La carpeta **addons** contiene complementos personalizados. Sólo tienes que poner tus addons personalizados si tienes alguno.

# Odoo configuration

Para cambiar la configuración de Odoo, edite el archivo **etc/odoo.conf**.

# Access to PgAdmin:

Puedes usar PgAdmin si lo necesitas. Está en el puerto 5050 (127.0.0.1:5050 por ejemplo) y las credenciales por defecto son:

* email: pgadmin4@pgadmin.org
* password: admin

Si no necesitas PgAdmin, puedes comentarlo o eliminarlo en docker-compose.yml.

# Add a new server in PgAdmin:

* Host name/address: db
* Port: 5432
* Username as POSTGRES_USER: odoo
* Password as POSTGRES_PASSWORD: odoo

# docker-compose.yml

* odoo:14
* postgres:13
* pgadmin4
