## Muestras de ejecución

### Iniciar compose
![compose up](/capturas/1.png)


### Odoo iniciado
![odoo up](/capturas/2.png)
DB: demo1
MAIL: admin@admin.com
PASS: renaido


### Dentro de Odoo
![odoo in](/capturas/3.png)


### 2 Bases de Datos
![bases](/capturas/4.png)


### PgAdmin
![pgAdmin](/capturas/pg1.png)


### Comprobando PgAdmin
![pgAdmin](/capturas/pg2.png)




## Incidencias
condition: service_healthy
### 1: depends_on

Al tratar de iniciar el docker, me salió este error
        validating /home/dam26/Diego/SXE/odoo/docker-compose.yml: services.odoo.depends_on must be a list

Esto debido a que mi estructura era erronea

Antes (mal):
        odoo:
            image: odoo:${ODOO_TAG}
        depends_on:
        db:
        condition: service_healthy

Ahora (bien):
        odoo:
            image: odoo:${ODOO_TAG}
        depends_on:
            db:
                condition: service_healthy