#LATAM Account Type Group
![Ventana de configuración](MainPage.png)
##Descripción
Mestro de grupo de tipo de cuenta. Crea una tipificación para un tipo de cuenta y asociar a este tipo un conjunto de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que tendrá acceso. Los tipos de cuenta son:

* Cliente
* Proveedor
* banco
* Inventario
* Ledger??


## Sección General
###Campos

>####Tipo de cuenta
>>**Descripcion**: Especifica a que tipo de cuenta va a tipificar. 

>>> * Cliente
>>> * Proveedor
>>> * banco
>>> * Inventario
>>> * Ledger??

un grupo tipo cuenta cuyo Tipo cuenta es cliente solo puede ser usado en la extension de cliente. Uno tipo proveedor solo puede tipificar a proveedores y asi sucesivamentes.
>>**Tipo**:Code

>####No.
>>**Descripcion**: 
	
>>**Tipo**:Code

>####Descripción
>>**Descripcion**: 
	
>>**Tipo**:Code

## Sección clase de comprobante Cliente/Proveedor 
###Campos
>####Clase de comprobante
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md)
	
>>**Tipo**:Code

>####Descripción
>>**Descripcion**: 
	Descripción de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md)
	
>>**Tipo**:Text

## Sección Clase de comprobante por defecto de cliente
###Campos
>####Clase de comprobante
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md)
	
>>**Tipo**:Code

>####Descripción
>>**Descripcion**: 
	Descripción de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md)
	
>>**Tipo**:Text

## Sección Clase de comprobante por defecto de proveedor
###Campos
>####Diario de crédito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Diario de débito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Medio de pago predeterminado
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear un medio de cobro pago. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Remito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Diario de débito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Diario de débito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Diario de débito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]

>####Diario de débito
>>**Descripcion**: 
	Id de [clases de comprobantes](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md) que será propuesto como clase de comprobante por defecto al crear una entrada en diario de crédito. En este campo solo pueden cargarse comprobante cuya clase de comprobante tenga marcado el check 
	
>>**Tipo**:Code[15]


