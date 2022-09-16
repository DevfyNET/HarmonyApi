# HarmonyApi


## EndPoint Api
- http://172.16.28.4:3001/api/

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
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura/{{ ID Factura }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura/0 <br>
Al enviar el valor de ***0*** el Api entiende que tiene que devolver todas las facturas

### Mostrar solo una factura
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura/{{ ID Factura }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura/48 <br>
***48*** es el id de la factura


### Mostrar detalle una factura
~~~
 http://172.16.40.63:3001/api/{{ Usuario }}/{{ Llave Acceso }}/caps/hh-factura-detalle/{{ ID Factura }}
~~~
- http://172.16.40.63:3001/api/8z4WsOYqHM/QPNT50byugANM1HWeZ6xcxEorVQzrTfY/caps/hh-factura-detalle/48 <br>
***48*** es el id de la factura
