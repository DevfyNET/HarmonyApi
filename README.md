# HarmonyApi


## EndPoint Api
- http://172.16.40.63:3001/api/

## Configuración
El api necesita de un usuario y una llave de acceso, la cual sera otorgada por el administrador del sistema, un ejemplo seria el siguiente:
http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/home <br>
En el ejemplo anterior ***8z4WsOYqHM*** es el usuario y ***QPNT50byugANM1HWeZ6xcxEorVQzrTfY*** es la llave de acceso, ambas necesarias para acceder al Api y tener una respuesta validad.<br>
***La anterior llave de acceso y usuarios no son válidos, son para efecto del ejemplo, el administrador proporcionara la llave de acceso.***  <br>
El usuario que necesite acceso al Api fuera de la red, tendra que hacerlo por medio de una VPN, dicho acceso será otorgado por el administrdor de la red.

## Consultas válidas

### Información Api
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/home

### Mostrar todas las facturas
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura/0/0/0
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura/0 <br>
Al enviar el valor de ***0*** el Api entiende que tiene que devolver todas las facturas

### Mostrar solo una factura
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura/{{ ID Factura }}/{{ Fecha Desde }}/{{ Fecha Hasta}}}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura/48/20221201/20221230<br>
***48*** es el id de la factura<br>
El formato de la fecha desde y hasta tiene que ser en el siguiente ***20221201(Año, Mes y Día), sin guiones y todo junto***. <br>
Al enviar el valor de 0 el Api entiende que tiene que devolver todos las facturas.


### Mostrar detalle una factura
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura-detalle/{{ ID Factura }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura-detalle/48 <br>
***48*** es el id de la factura

### Cargar Facturas
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-check
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-check <br>

### Cargar Detalle Facturas
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/check-detail
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/check-detail <br>

### Factura con detalle
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/factura/{{ ID Factura }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/factura/20467 <br>


## Oracle Opera

### Folios
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/opera/oracle/folio/{{ Numero de folio }}/{{ Fecha Desde }}/{{ Fecha Hasta }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/opera/oracle/folio/4622/20221201/20221230 <br>
>El formato de la fecha desde y hasta tiene que ser en el siguiente ***20221201(Año, Mes y Día), sin guiones y todo junto***. <br>
>Al enviar el valor de 0 el Api entiende que tiene que devolver todos los folios ya sea folio o por fechas.

### Reporte In House
| Metodo Request |
| -------------- |
|       GET      |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/opera/oracle/reporte/in-house
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/opera/oracle/reporte/in-house <br>

### Cargo Habitación
| Metodo Request |
| -------------- |
|       POST     |
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/opera/oracle/cargo/habitacion/
~~~

<ul>
<li><p>El "room" es la habitación</p></li>
<li><p>El "amount" es el monto total</p></li>
<li><p>El "nro_cheque" es el numero de cheque, <strong>(Se permite que sea nulo, para que sea nuelo tiene que enviar de valor un cero)</strong></p></li>
<li><p>El "resv_name" es el numero de reserva</p></li>
<li><p>El "quantity" es la cantidad de productos o lineas ingresadas</p></li>
<li><p>El "reference" es un texto de referencia <strong>(Se permite que sea nulo, para que sea nuelo tiene que enviar de valor un cero)</strong></p></li>
<li><p>"trx_code"</p></li>
<li><p>El "price_per_unit" es el precio por unidad</p></li>
<li><p>El "IVA", es si el producto o linea lleva o no IVA</p>
<ul>
 <li><p>El "amount_iva" es el monto del IVA</p></li>
 <li><p>El "price_per_unit_iva" el monto del IVA por producto o linea</p></li> 
</ul>
</li>
</ul>

###### Ejemplo del Body request JSON
```JSON
{
    "room": "9060",
    "amount": 30,
    "nro_cheque": "7978",
    "resv_name": "219326",
    "quantity": 1,
    "reference": "Referencia de Prueba",
    "trx_code": "7003",
    "price_per_unit": 30,
    "IVA": 1,
    "amount_iva": 3.9,
    "price_per_unit_iva": 3.9
}
```
###### Mensaje de Respuesta exitoso
```JSON
{
    "msj": "Cargo habitación exitoso"
}
```
