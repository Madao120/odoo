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
(luego cree otra que se llama demo a secas, es donde realicé las capturas)

### PgAdmin
![pgAdmin](/capturas/pg1.png)


### Comprobando PgAdmin
![pgAdmin](/capturas/pg2.png)


## Ejercicio 1
Captura de cada tipo de producto

### Producto con rastreo inventario
![con inventario](/capturas/productos1.png)


### Proc¡ducto sin rastro inventario
![con inventario](/capturas/productosinrastreo.png)

### Producto de Servicio
![con inventario](/capturas/producto_servicio.png)


### Producto de Combinación
![con inventario](/capturas/producto_combinacion.png)


## Ejercicio 2 Recorrido

### Contacto - Persona
![con inventario](/capturas/recorridoindividuo.png)

### Contacto - Compañía
![con inventario](/capturas/recorrido_compañia.png)

### Contacto Creación
![con inventario](/capturas/recorrido_crear_individuo.png)

### Producto Hora soporte
![con inventario](/capturas/recorrido_servicio.png)

### Producto Libro
![con inventario](/capturas/recorrido_crear_bien.png)

### Presupuesto de cliente - pedido de venta
![con inventario](/capturas/recorrido_presupuesto.png)


### Facturación - Proveedor

![con inventario](/capturas/recorrido_presupuesto_facturar.png)

### Facturación - Cliente
![con inventario](/capturas/facturacion_cliente.png)

### Chatter - Programar actividad
![con inventario](/capturas/Programar%20Actividad.png)


## Ejercicio 3

### Guardar Filtro
![con inventario](/capturas/Filtro%20Custom.png)

## Ejercicio 4

### Desarrollador - Contacto
![con inventario](/capturas/desarrollador_contacto.png)
- Campo1: Nombre
- Nombre: complete_name
-------------------
- Campo2: Correo Electrónico
- Nombre: email

### Desarrollador - Factura
![con inventario](/capturas/desarrollador_factura.png)
- Campo1: Cliente
- Nombre: parthner_id
-------------------
- Campo2: Fecha de Creación
- Nombre: create_date

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
### 2: Contraseña
Al asignar la contraseña en el compose pensaba que era la de postgress, ya que es la que habia asignado en el campo PASSWORD, pero la contraseña es la de odoo.conf, el campo admin_password.

## USO DE IA
 Esta vez solo la utilicé para ver los fallos al iniciar el odoo.<br>
 Básicamente las incidencias mencionadas, donde le pasé el docker-compose una vez hecho para que me dijera que estaba mal tabulado un campo a demás de que le pregunté cuando utilicé mal la contraseña, donde me dijo que no era la de postgress.