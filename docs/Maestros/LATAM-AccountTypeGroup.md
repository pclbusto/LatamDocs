# LATAM Account Type Group
![Ventana de configuración](../../Imagenes/LATAM-AccountTypeGroup-MainPage.PNG)
## Descripción
Mestro de grupo de tipo de cuenta. Crea una tipificación para un tipo de cuenta y asociar a este tipo un conjunto de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que tendrá acceso. Los tipos de cuenta son:

* Cliente
* Proveedor
* banco
* Inventario
* Ledger??


## Sección General
### Campos

>#### Tipo de cuenta
>>**Descripción**: Especifica a que tipo de cuenta va a tipificar. 

>>> * Cliente
>>> * Proveedor
>>> * banco
>>> * Inventario
>>> * Ledger??

un grupo tipo cuenta cuyo tipo cuenta es `cliente` solo puede ser usado en la extensión de cliente. Uno tipo proveedor solo puede tipificar a proveedores y así sucesivamente.
>>**Tipo**:Code

>#### No.
>>**Descripción**: 
	
>>**Tipo**:Code

>#### Descripción
>>**Descripción**: 
	
>>**Tipo**:Code

## Sección clase de comprobante Cliente/Proveedor 
### Campos
>#### Clase de comprobante
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md)
	
>>**Tipo**:Code

>#### Descripción
>>**Descripción**: 
	Descripción de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md)
	
>>**Tipo**:Text

## Sección Clase de comprobante por defecto de cliente
### Campos
>#### Nota de crédito de servicio
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una nota de crédito de servicio. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Notas de crédito de servicio](../Maestros/LATAM-VoucherClassType.md#notas-de-credito-de-servicio)
	
>>**Tipo**:Code[15]

>#### Factura de servicio
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una factura de servicio. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Factura de servicio](../Maestros/LATAM-VoucherClassType.md#factura-de-servicio) 
	
>>**Tipo**:Code[15]

>#### Remito de servicio
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear un remito de servicio. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Remito](../Maestros/LATAM-VoucherClassType.md#remito)  
	
>>**Tipo**:Code[15]

>#### Remito
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear un remito de compra/ventas. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Remito](../Maestros/LATAM-VoucherClassType.md#remito)
	
>>**Tipo**:Code[15]

>#### Nota de crédito de proyecto
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una nota de crédito de proyecto. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check nota de crédito de proyecto](../Maestros/LATAM-VoucherClassType.md#notas-de-credito-de-proyecto) 
	
>>**Tipo**:Code[15]

>#### Factura de proyecto
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una factura de proyecto. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Factura de proyecto](../Maestros/LATAM-VoucherClassType.md#factura-de-proyecto) 
	
>>**Tipo**:Code[15]

>#### Remito de proyecto
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear un remito de proyecto. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Remito de proyecto](../Maestros/LATAM-VoucherClassType.md#remito-de-proyecto)
	
>>**Tipo**:Code[15]

>#### Remisión de devolución de proyecto
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una devolución de proyecto. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Remito de devolución](../Maestros/LATAM-VoucherClassType.md#remito-devolucion)
	
>>**Tipo**:Code[15]

>#### Remisión de reembolso
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el FALTA 
	
>>**Tipo**:Code[15]

>#### Nota de crédito de venta
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una nota de crédito de ventas. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Nota de crédito de venta](../Maestros/LATAM-VoucherClassType.md#notas-de-credito-de-ventas) 
	
>>**Tipo**:Code[15]

>#### Factura de venta
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una factura de ventas. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el [check Factura de venta](../Maestros/LATAM-VoucherClassType.md#factura-ventas)  
	
>>**Tipo**:Code[15]




## Sección Clase de comprobante por defecto de proveedor
### Campos
>#### Diario de crédito
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Diario de débito
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Medio de pago predeterminado
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear un medio de cobro pago. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Remito
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Nota de crédito de compra
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Factura de compra
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Remisión de reembolso
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>#### Diario de débito
>>**Descripción**: 
	Id de [clases de comprobantes](../Maestros/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo se pueden cargar comprobante cuyo tipo clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]


