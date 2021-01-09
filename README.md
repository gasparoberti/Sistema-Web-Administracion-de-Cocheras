# Sistema-Web-Administracion-de-Cocheras
Proyecto final de carrera realizado para Mutual de Ingeniería de Santa Fe.

Login

![Screenshot_1](https://user-images.githubusercontent.com/45102218/104094892-7ce40600-5272-11eb-8be1-b74957f4089e.png)

Administración de cocheras

Cada fila de la tabla cuenta con una serie de acciones para cada cochera que pueden ser accedidas por los administradores del sistema:
Modificar,
Eliminar,
Listar Registros de la Cochera,
Listar Tarifas de la Cochera,
Listar Usuarios Asociados a la Cochera,
Agregar Usuarios a la Cochera.

![Screenshot_2](https://user-images.githubusercontent.com/45102218/104094919-adc43b00-5272-11eb-9c0d-81381da9e028.png)
![Screenshot_3](https://user-images.githubusercontent.com/45102218/104094924-b288ef00-5272-11eb-8539-be3b7244e8e3.png)


Administración de usuarios

Los usuarios son los empleados capaces de manipular el sistema. Estos pueden ser Playeros o Administradores. Según el rol que tengan son las funciones que podrán realizar.

![Screenshot_4](https://user-images.githubusercontent.com/45102218/104095115-ddc00e00-5273-11eb-9c43-fe8776671981.png)
![Screenshot_5](https://user-images.githubusercontent.com/45102218/104095119-e0226800-5273-11eb-9d9f-aebc3fabe438.png)

Administración de tarifas

Una Tarifa es un período de tiempo en horas dentro de un día. Una tarifa a su vez puede tener rangos de tiempos en los cuales el precio puede o no ser el mismo. 
El objetivo principal de una tarifa es poder contemplar la situación de que en un mismo día se pueda tener distintos tipos de cobros. Valor es una constante que sirve para poder realizar esta distinción. Cuando vale 1 el valor calculado como la suma de los distintos valores de cada rango no varía. Cuando es 1.5 por ejemplo, el valor será un 50% más.
Para cada tarifa se pueden realizar las siguientes acciones:
Modificar,
Eliminar,
Listar Rangos Horarios Asociados.

![Screenshot_7](https://user-images.githubusercontent.com/45102218/104095187-2d9ed500-5274-11eb-8626-05551fb641d9.png)

Para asignar un rango a una tarifa se debe seleccionar la acción 3 que se encuentra dentro de las acciones del lado derecho para una tarifa. Al seleccionar este botón aparecerá un listado con todos los rangos que la tarifa tiene asignados. 

![Screenshot_9](https://user-images.githubusercontent.com/45102218/104095448-989cdb80-5275-11eb-8749-5756ffd6a425.png)
![Screenshot_8](https://user-images.githubusercontent.com/45102218/104095396-57a4c700-5275-11eb-82f6-302aacd7d031.png)

Administración de Rangos Horarios

Un Rango Horario es un período de tiempo en minutos dentro de una Tarifa. El objetivo principal de un rango es poder dividir la tarifa en distintos lapsos de tiempo donde cada uno tiene un precio. 
Para cada tarifa se pueden realizar las siguientes acciones:
Modificar,
Eliminar.

![Screenshot_10](https://user-images.githubusercontent.com/45102218/104095501-e9accf80-5275-11eb-9ca5-8ae842238127.png)

Asignación de Tarifas a una Cochera

![Screenshot_11](https://user-images.githubusercontent.com/45102218/104095584-7192d980-5276-11eb-97d6-e9be3685fe9b.png)

Administración de Registros

Una estadía es una estancia o permanencia durante cierto tiempo en el estacionamiento mientras que un registro es la acción de registrar una estadía en el estacionamiento.
Para listar los registros se debe seleccionar la acción 3 que se encuentra dentro de las acciones del lado derecho para una cochera. Al seleccionar este botón aparecerá el listado con los registros pertenecientes a esa cochera. Por defecto aparecen todos los registros que existen desde el día de la fecha hasta un año atrás. Además se cuenta con un filtro para listar según las siguientes opciones:
Fecha Desde - Fecha Hasta.
Mensualizado: Registro de un vehículo perteneciente a un socio que abona mensualmente.
Medido: Registro de un vehículo que permanecerá un período de tiempo.
Cerrado: Estado de un registro medido en el que el vehículo ya se retiró del estacionamiento. Posee fecha de ingreso y de egreso y total cobrado.
Abierto: Estado de un registro medido en el que el vehículo permanece en el estacionamiento. Solo posee fecha de ingreso.
Por defecto aparecen todas las opciones desmarcadas.
    
![Screenshot_12](https://user-images.githubusercontent.com/45102218/104095634-b159c100-5276-11eb-96be-1ab2516ee5ed.png)

El objetivo principal de un registro es poder almacenar el ingreso y egreso de vehículos del estacionamiento.
Para cada registro se pueden realizar las siguientes acciones:
Modificar,
Cerrar.

![Screenshot_13](https://user-images.githubusercontent.com/45102218/104095664-e108c900-5276-11eb-8701-e15cfba4bd69.png)

El formulario no se envía hasta que los datos no son correctos. Cuando esto ocurre, si no hay ningún error con el servidor de datos el sistema muestra el ticket de ingreso de la siguiente forma y luego en el listado aparece el nuevo registro.

![Screenshot_14](https://user-images.githubusercontent.com/45102218/104095684-00075b00-5277-11eb-97e0-4bd513b7c962.png)

Sólo se pueden modificar o cerrar registros que no hayan egresado. Si ya egresaron el sistema muestra el error en el formulario.

![Screenshot_15](https://user-images.githubusercontent.com/45102218/104095721-3ba22500-5277-11eb-8113-950803de083f.png) 
![Screenshot_16](https://user-images.githubusercontent.com/45102218/104095722-3e047f00-5277-11eb-9aea-70d998077666.png)

Validación Código de Descuento

El código de descuento es un beneficio opcional que puede ser obtenido por la persona antes de concurrir al establecimiento. Solicitado a través de la aplicación de la Mutual es proporcionado al momento del ingreso. Al realizar el registro de ingreso se valida con la base de datos de la empresa, en caso de ser correcto el registro tendrá un código de descuento asociado. Si este código se valida correctamente, al momento de realizar el egreso se descontarán de los minutos una cierta cantidad según la tarifa. Esta cantidad se define al momento de asociar la tarifa con una cochera específica, por lo que los minutos de descuentos pueden variar para distintas cocheras por más de ser la misma tarifa. 
Por cada registro se puede tener un solo código de descuento, por lo tanto se debe saber si el descuento ya fue usado debido a que un registro puede tener más de una tarifa. En caso de que ocurra esto el descuento se realizará solo en la primer tarifa restando cantidad de minutos respectiva. 

![Screenshot_17](https://user-images.githubusercontent.com/45102218/104095824-bcf9b780-5277-11eb-8eb5-5e20dfcfb281.png)

Administración de Estadísticas

Para calcular las estadísticas se hace un recorrido por los registros que existen, y a partir de estos se recopila la información necesaria para el análisis que desee la empresa. Los informes analizan las siguientes variables para cada cochera:

Vehículos medidos por hora,
Vehículos medidos por día,
Cantidad de registros (medidos y mensualizados).

![Screenshot_18](https://user-images.githubusercontent.com/45102218/104095871-f7fbeb00-5277-11eb-855f-d5d439f85a60.png)


