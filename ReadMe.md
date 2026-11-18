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

### Facturación con IVA reflejado
![con inventario](/capturas/factura_iva_bien.png)
Quiero aclarar que esta es una corrección, por ello no es la misma factura que aparecerá más a delante, en esta imagen el iva si que se refleja correctamente tanto en el bien como en el servicio.

### facturación impreso
![con inventario](/capturas/recorrdo_impreso.png)

### Facturación PAGADO
![con inventario](/capturas/recorrido_pagado.png)


### Facturación - Proveedor
![con inventario](/capturas/facturacion%20proveedor.png)

### Facturación - Cliente
![con inventario](/capturas/facturacion_cliente.png)

### Chatter - Programar actividad
![con inventario](/capturas/Programar%20Actividad.png)


## Ejercicio 3

### Guardar Filtro
![con inventario](/capturas/Filtro%20Custom.png)

## Ejercicio 4

### Activar modo desarrollador

#### Mediante Ruta
Se deberá de poner lo siguiente en la url
http://localhost:8069/odoo?debug=1

![con inventario](/capturas/activar_desarrollador1.png)

#### Mediante Ajustes
Debemos de ir a Ajustes, y en la primera pestaña bajar a la parte más baja de la misma.
![alt text](/capturas/activar_desarrollador2.png)

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
- Nombre: partner_id
-------------------
- Campo2: Moneda
- Nombre: currency_id

## Incidencias
condition: service_healthy

### 1: depends_on
*NO LO PONGO EN TABLA POR EL FORMATO DE EXPLICACIÓN

Fecha: 4/11/2026

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
| Fecha | Síntoma / Problema | Causa | Solución |
| :--- | :--- | :--- | :--- |
| 10/11/2026 | Error al iniciar sesión en odoo | Al asignar la contraseña en el compose pensaba que era la de postgress, ya que es la que habia asignado en el campo PASSWORD | pero la contraseña es la de odoo.conf, el campo admin_password. |


## USO DE IA
 Esta vez solo la utilicé para ver los fallos al iniciar el odoo, esto con **chatgpt** en preguntas puntuales.<br>
 Básicamente las incidencias mencionadas, donde le pasé el docker-compose una vez hecho para que me dijera que estaba mal tabulado un campo a demás de que le pregunté cuando utilicé mal la contraseña, donde me dijo que no era la de postgress.