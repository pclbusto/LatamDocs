#LATAM Extensión de documento
![Ventana de configuración](MainPage.png)

##Descripción
Extensión a documentos nativos de Business Central. Como las extensiones tienen un comportamiento similar para los distintos documentos:

* Facturas de ventas.
* Facturas de compra.
* Devoluciones de ventas.
* Devoluciones de compras.
* Ordenes de compras.
* Ordenes de venta. 

Esta entidad se usa para todos estos documentos de forma similiar y variando un poco el comportamiento de algunas de sus partes dependiendo la entidad con la que se está trabajando. Los tipos de entidad son:

* Cuenta GL
* Cliente
* Proveedor
* Banco 
* Activo Fijo

Dependiendo del tipo de documento es el tipo de entidad con el que se trabaja. 

Documento|Entidad
---------|:-------:
Facturas de ventas|Cliente
Devoluciones de ventas|Cliente
Remitos (se crean de Orden de venta)|Cliente
Facturas de compra|Proveedor





## Sección LATAM
###Campos
***
>####Clase de comprobante
>>**Descripción**: id de clase de comprobante ver [Clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md). 

>>**Tipo**:Code[15]

>>**Filtrado:** Este lookup tiene un filtro complejo. Como primera estapa de filtrado, divide el grupo en dos parte. Una todo aquellos comprobantes que no son medios de cobro pago (MCP) y los que son ver [Clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md).<br>
Para los que no son MCP los comprobantes a mostrar van a depender de el tipo de documento que se este extendiendo. La clase de comprobante tiene una tipificación, esta tipificacion se la da el [tipo de clase de comprobante cargada en la clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md#tipo-clase-comprobantes). Mediante este campo se especifica donde puede ser usado dicho comprobante. Por ejemplo Si estamos creando una factura de ventas, el tipo de la clase de comprobante en la sección de facturas debe tener marcado que es [Factura Ventas](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-ventas). Este mismo comportamiento se aplica para los demás documentos. Esto forma parte del filtrado para comprobantes. Siguiendo con el ejemplo tenemos también la entidad que participa en el documento, en el ejemplo estamos en una factura de ventas entonces la entidad es cliente. El cliente en su extension tiene un campo que se llama [grupo tipo cuenta](../Maestros/LATAM-AccountTypeGroup/LATAM-AccountTypeGroup.md#seccion-clase-de-comprobante-clienteproveedor). En el maestro de grupo tipo de cuenta hay una lista de comprobantes. Ahora filtro toma en cuenta esta lista y solo va a mostrar aquellos comprobantes que esten en esta lista.
Para resolver esta situación lo que se armó es una [query](../Desarrollo/Queries/LATAM-VoucherClassLookup/LATAM-VoucherClassLookup.md) en AL/Code que hace un join entre las tablas de comprobante, tipo clase de comprobante, y los comprobantes que tiene asociado cada grupo de cliente o grupo de proveedor mediante la entidad [grupo tipo cuenta](../Maestros/LATAM-AccountTypeGroup/LATAM-AccountTypeGroup.md#seccion-clase-de-comprobante-clienteproveedor).
Dependiendo del documento en el que se este trabajando los comprobantes cuyo tipo sea compatible son:

>>|Documento|Sub documento|Tipo de comprobantes|
|---------|-------------|:------------------:|
Facturas de ventas||[Factura de ventas](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-ventas)
Facturas de servicio||[Factura de servicio](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-de-servicio)
Facturas de compras||[Factura de compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-compras)
Orden de ventas|Remito de ventas|[Remito](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#remito)
Orden de ventas|Factura de ventas|[Factura de ventas](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-ventas)
Orden de compras|Remito de compras|[Remito de compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-ventas)
Orden de compras|Factura de compras|[Factura de compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#factura-ventas)
Nota de crédito de ventas||[Notas de crédito de ventas](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#notas-de-credito-de-ventas)
Nota de crédito de servicio||[Notas de crédito de servicio](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#notas-de-credito-de-servicio)
Nota de crédito de compra||[Notas de crédito de compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#remito)
Orden de devoluciones de ventas|Remito devolución ventas|[Remito devolución venta](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#remito-devolucion)
Orden de devoluciones de ventas|Nota de crédito|[Notas de crédito de ventas](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#notas-de-credito-de-ventas)
Orden de devoluciones de Compras|Remito devolución compras|[Remito devolución compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#remito-devolucion)
Orden de devoluciones de Compras|Notas de crédito de compras|[Notas de crédito de compras](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md#remito-devolucion)


>####Descripción
>>**Descripción**: Descripción del Id de clase de comprobante [Clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md)
	
>>**Tipo**:Code[30]

>####Punto de venta
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####Prefijo
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####Número de documento
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####Número de documento completo
>>**Descripción**: Es el resultado de la concatenación de:

>>>* [prefijo del comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md#prefijo): si el prefijo es ''. Y el prefijo mas el [separador del comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md#separador) si es distinto de ''.

>>>* El [prefijo del punto de ventas](../LATAM-DocumentExtension/LATAM-DocumentExtension.md#prefijo):  si el prefijo es ''. Y el prefijo mas el [separador del comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md#separador) si es distinto de ''.

>>>* El [número de comprobante]().
	
	
>>**Tipo**:Code[30]

>####Fecha de documento
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####Fecha vencimiento
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]
***
## Sección contribuyentes
![Ventana de configuración](Seccion-Contribuyentes.png)
##Descripción
Esta sección contiene info adicional sobre el contribuyente. Puede ser habilitada mediante la configuración de detalla contribuyente en [Clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md). Si se tiene marcada esta opción los campos de toda la sección deberían estar como requerido. Los campos de esta sección también pueden ser habilitados uno a uno, en la sección de datos adicionales en [Clase de comprobante](../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md).

###Campos
***
>####Tipo contribuyente
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####Nombre compañía
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]

>####País radicación
>>**Descripción**: 
	
	
>>**Tipo**:Code[30]
***
