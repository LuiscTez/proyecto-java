# Proyecto factura Java

Proyecto en java para el registro de facturas.

## Instalación:
1. git clone https://github.com/LuiscTez/proyecto-java.git
2. Ejecutar desde el archivo Application.java

## Base de datos:
El proyecto funciona con una base de datos llamada base_factura, con las siguientes tablas:
```sql
CREATE TABLE factura (
  id_factura int(11) NOT NULL AUTO_INCREMENT,
  fecha date NOT NULL,
  cliente varchar(100) NOT NULL,
  total decimal(10,2) NOT NULL,
  PRIMARY KEY(id_factura)
);

CREATE TABLE detalle_factura (
  id_detalle int(11) NOT NULL AUTO_INCREMENT,
  id_factura int(11) NOT NULL,
  producto varchar(100) NOT NULL,
  cantidad int(11) NOT NULL,
  precio_unitario decimal(10,2) NOT NULL,
  subtotal decimal(10,2) NOT NULL,
  PRIMARY KEY(id_detalle),
  FOREIGN KEY(id_factura) REFERENCES factura(id_factura)
);
```

## Driver de conexion a base de datos:
Incluir el driver en el paquete librerias del proyecto.
