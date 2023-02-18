
# Mercadito
## Normalización

 - Administracion Base de Datos
 - Catedratico: Ivan Cruz 
 - Alumno: Maria Alejandra Funez Perez 
 - N° Cuenta: 61951373
 - Fecha: 16 de febrero de 2022


## Análisis
--Se debe normalizar la base de datos en al menos un caso (1FN, 2FN, 3FN) según sea necesario para lograr una mayor calidad en la estructura de la base de datos:


**Tabla sin normalizacion**
**Tabla Mercadito**

|ID|NOMBREPROVEEDOR|NOMBREPRODUCTO|CANTIDAD|PRECIO|RTN|TELEFONO|CORREO|DIRECCION|ESTADO|CATEGORIA|DIA|MES|AÑO|USUARIOCREACION|
|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|
|1|EMPRESA AH|POLLO|10|100|050119981090231|99898888|AH@GMAIL.COM|PUERTO CORTES|1|Contado|16|02|2023|ADMIN|
|2|MERCADITO|REFRESCO|10|100|050119981090231|99898888|MERCA@GMAIL.COM|PUERTO CORTES|1|Credito|16|02|2023|ADMIN|


## Aplicación:
**1FN**
La tabla no cumple con la **1FN** ya que en el campo vemos un grupo de datos relacionados que se pueden manejar en tablas y los campos **Dia**, **Mes** y **Año**. 
Aplicando la **1FN** la tabla quedaria de la siguiente manera:

**Tabla Proveedores**

|IDPROVEEDOR|NOMBRE|IDENTIFICACION|RTN|TELEFONO|CORREO|DIRECCION|ESTADO|CATEGORIA|FECHACREACION|USUARIOCREACION|
|--|--|--|--|--|--|--|--|--|--|--|
|1|EMPRESA AH|05011998109023|050119981090231|99898888|AH@GMAIL.COM|PUERTO CORTES|Activo|Credito|2023-02-16|ADMIN|
|2|MERCADITO|05011998109023|050119981090231|99898888|MERCA@GMAIL.COM|PUERTO CORTES|Activo|Contado|2023-02-16|ADMIN|


**Tabla Productos**

|IDPRODUCTO|IDPROVEEDOR|NOMBRE|CODIGO|CANTIDAD|PRECIO|FECHACREACION|USUARIOCREACION|
|--|--|--|--|--|--|--|--|
|1|1|REFRESCO AH|05011|100|50|2023-02-16|ADMIN|
|2|1|POLLO|05193|80|20|2023-02-16|ADMIN|



**2FN**
Vemos que la tabla no cumple con la 2FN ya que se podrian crear tablas separadas para **categoria de proveedores**. Cada una de estas tablas tendría su clave primaria y estarían relacionadas por una clave externa (Foreign Key).

Aplicando la **2FN** las tablas quedarian de la siguiente manera:

**Tabla Categoria de proveedores**

|IDCATEGORIAPROVEEDOR|DESCRIPCION|ESTADO|FECHACREACION|USUARIOCREACION|
|--|--|--|--|--|
|1|Credito|Activo|2023-02-16|ADMIN|
|2|Contado|Activo|2023-02-16|ADMIN|


**3FN**
La 3FN ya esta aplicada, ya que las tablas cumplen con todos los requisitos de la normalizacion. La tabla quedaria de la siguiente manera


**Tabla Proveedores**

|IDPROVEEDOR|IDCATEGORIAPROVEEDOR|NOMBRE|IDENTIFICACION|RTN|TELEFONO|CORREO|DIRECCION|ESTADO|FECHACREACION|USUARIOCREACION|
|--|--|--|--|--|--|--|--|--|--|--|
|1|1|EMPRESA AH|05011998109023|050119981090231|99898888|AH@GMAIL.COM|PUERTO CORTES|Activo|2023-02-16|ADMIN|
|2|1|MERCADITO|05011998109023|050119981090231|99898888|MERCA@GMAIL.COM|PUERTO CORTES|Activo|2023-02-16|ADMIN|


**Tabla Productos**

|IDPRODUCTO|IDPROVEEDOR|NOMBRE|CODIGO|CANTIDAD|PRECIO|FECHACREACION|USUARIOCREACION|
|--|--|--|--|--|--|--|--|
|1|1|REFRESCO|05011|100|50|2023-02-16|ADMIN|
|2|1|POLLO|05193|80|20|2023-02-16|ADMIN|

