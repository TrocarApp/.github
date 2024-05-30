

![Image](https://github.com/orgs/TrocarApp/projects/4/assets/1991984/cbe69e11-77c7-4729-b7e6-078d673a5922)



**Tabla products**

- **id** = uuid único clave primaria
- **name** = string de 255 - obligatorio - Representa en nombre del producto o servicio
- **description** = string de 255 - opcional - Una breve descripción del producto
- **price** = número decimal de 10, 6 - opcional - Representa el valor monetario del producto con un valor de hasta 10 números a la izquierda y 6 decimales
- **image_url** = campo de tipo text - opcional - Almacena la url de la imagen principal del producto
- **availability** = string de 255 - opcional - Representa la disponibilidad del producto
- **stock** = número entero - default 1 - Representa la cantidad de productos disponibles en almacén
- **category_id** = uuid - opcional - Clave foránea relacionada con el id de la tabla categories
- **type** = enum - valores product, service - Define el tipo de item si es producto o servicio
- **created_by** = número entero - obligatorio - Relacionado con el id de la tabla de usuarios y define el propietario del producto
- **deleted_at** = tipo timestamp - Permite hacer un borrado suave del registro sin perder los datos.
- **created_at** = tipo timestamp - Fecha en que fue creado el registro
- **updated_at** = tipo timestamp - Fecha de la ultima actualización del registro

**Tabla product_attributes**

- **id** = número entero - único - autoincremental
- **product_id** - uuid - borrado en cascada - Clave foránea relacionada con el id de la tabla de productos
- **name** - string de 255 - Representa la clave o el título del atributo a asignar
- **data_type** - string de 255 - Representa el valor del atributo a asignar
- **created_by** = número entero - obligatorio - Relacionado con el id de la tabla de usuarios
- **created_at** = tipo timestamp - Fecha en que fue creado el registro
- **updated_at** = tipo timestamp - Fecha de la ultima actualización del registro

**Tabla categories**

- **id** = uuid único clave primaria
- **name** - string de 255 - obligatorio - Representa la clave o el título del categoría
- **description** = string de 255 - opcional - Una breve descripción de la categoría
- **created_by** = número entero - obligatorio - Relacionado con el id de la tabla de usuarios
- **created_at** = tipo timestamp - Fecha en que fue creado el registro
- **updated_at** = tipo timestamp - Fecha de la ultima actualización del registro
