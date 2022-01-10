# jmetertest
Jmeter test project

Documentación:
https://echo-serv.tbxnet.com/explorer/

NOTAS:
* El servicio de autentificación que deberia generarme el token según documentación del swagger (tbxnet auth - ${auth}) me está solicitando una autentificación por lo cual la ejecución de los demás servicios tiene errores. Sin embargo el proyecto está preparado para obtener el valor esperado en el response y pasarlo a todos hilos del proyecto.
* Para los servicios Echo, Mobile y Secret, se agrego un archivo csv para enviar de manera dinámica los parametros requeridos en el servicio.
* Para los servicios de System, se le agrego un escenario adicional para validar los headers en el request, percatandome que no existe ninguna validación con respecto a las cabeceras del servicio.

*******************************************************************************

Escenario para los servicios Echo:
* tbxnet text - ${parameter} = Consulta de manera dinámica el valor del parametro ingresado en el csv, validando el status code y los campos del response.
* tbxnet text - bad url - ${parameter} = Consulta de manera dinámica con una url incorrecta, validando el status code y los campos del response.  
* tbxnet text - bad request - ${parameter} = Consulta de manera dinámica con el parametro incorrecta, validando el status code y los campos del response.

Escenario para los servicios Mobile:
* tbxnet auth - ${auth} = Consulta de manera dinámica el valor del parametro ingresado en el csv, validando el status code y los campos del response.
* tbxnet auth - bad url - ${auth} = Consulta de manera dinámica con una url incorrecta, validando el status code y los campos del response.
* tbxnet auth - unexpected - ${auth} = Consulta de manera dinámica con el parametro incorrecta, validando el status code y los campos del response.

* tbxnet echo = Consulta el servicio validando el status code y los campos del response.
* tbxnet echo - bad url = Consulta el servicio con una url incorrecta, validando el status code y los campos del response.
* tbxnet echo - unauthorized = Consulta el servicio con un parametro incorrecto, validando el status code y los campos del response.

* tbxnet data = Consulta el servicio validando el status code y los campos del response.
* tbxnet data - bad url = Consulta el servicio con una url incorrecta, validando el status code y los campos del response.
* tbxnet data - unauthorized = Consulta el servicio con un parametro incorrecto, validando el status code y los campos del response.

Escenario para los servicios Secret:
* tbxnet secret files = Consulta el servicio validando el status code y los campos del response.
* tbxnet secret files - bad url = Consulta el servicio con una url incorrecta, validando el status code y los campos del response.
* tbxnet secret files - unauthorized = Consulta el servicio con un parametro incorrecto, validando el status code y los campos del response.

* tbxnet secret file name - ${auth} = Consulta de manera dinámica el valor del parametro ingresado en el csv, validando el status code y los campos del response.
* tbxnet secret file name - bad url - ${auth} = Consulta de manera dinámica con una url incorrecta, validando el status code y los campos del response.
* tbxnet secret file name - unexpected - ${auth} = Consulta de manera dinámica con el parametro incorrecta, validando el status code y los campos del response.

Escenario para los servicios System:
* tbxnet ping = Consulta el servicio validando el status code y los campos del response.
* tbxnet ping - bad url = Consulta el servicio con una url incorrecta, validando el status code y los campos del response.
* tbxnet ping - bad headers = Consulta el servicio con headers adicional e incorrectos, validando el status code y los campos del response.

* tbxnet version = Consulta el servicio validando el status code y los campos del response.
* tbxnet version - bad url = Consulta el servicio con una url incorrecta, validando el status code y los campos del response.
* tbxnet version - bad headers = Consulta el servicio con headers adicional e incorrectos, validando el status code y los campos del response.

Escenario para los servicios Test:
* tbxnet get test = Consulta el servicio validando el status code correcto.
* tbxnet post test = Consulta el servicio validando el status code correcto.
* tbxnet put test = Consulta el servicio validando el status code correcto.
* tbxnet delete test = Consulta el servicio validando el status code correcto.
* tbxnet patch test = Consulta el servicio validando el status code correcto.

