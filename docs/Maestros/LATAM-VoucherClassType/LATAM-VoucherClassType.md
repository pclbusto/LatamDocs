# LATAM Voucher Class Type
![Ventana de configuración](MainPage.png)

## Descripción
Este maestro es una tipificación para las [clases de comprobantes](../Maestros/LATAM-VoucherClassType/LATAM-VoucherClassType.md). Hay varias secciones en esta entidad, cada una representa un tipo de documento que puede ser usada en distintas entidades por ejemplo el grupo facturas tiene facturas de ventas, factura de compras, factura de servicios. Cada uno de estos check representa que puede ser usada como la extension de un determinado documento.

## Sección General
>#### No.
>>**Descripción**: 
	Identificador de tipo clase de comprobante.
	
>>**Tipo**:Code

>#### Descripción
>>**Descripción**: 
	texto descriptivo.
	
>>**Tipo**:text

>#### Prefijo
>>**Descripción**: 
	Cadena de caracteres limitada por el campo [long. prefijo tipo clase comprobante](../../LATAM-Setup/LATAM-Setup.md# long-prefijo-tipo-clase-comprobante), en la [configuración de latam](../../LATAM-Setup/LATAM-Setup.md)
	
>>**Tipo**:boolean


## Sección Medio Cobro Pago
![Ventana de configuración](Seccion-Collection-Payment-Document.png)
## Sección Facturas
![Ventana de configuración](Seccion-Invoices.png)

### Campos
>#### Factura Ventas
>>**Descripcion**: 
	Indica que puede ser usado en facturas de ventas.
	
>>**Tipo**:boolean

>#### Factura de servicio
>>**Descripcion**: 
	Indica que puede ser usado en facturas de servicio.
	
>>**Tipo**:boolean

>#### Factura Compras
>>**Descripcion**: 
	Indica que puede ser usado en facturas de compra.
	
>>**Tipo**:boolean

>#### Factura de proyecto
>>**Descripcion**: 
	Indica que puede ser usado en facturas de proyecto.
	
>>**Tipo**:boolean

## Sección notas de crédito
![Ventana de configuración](Seccion-CreditNote.png)

### Campos
>#### Notas de crédito de ventas
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de ventas.
	
>>**Tipo**:boolean

>#### Notas de crédito de servicio
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de servicio.
	
>>**Tipo**:boolean

>#### Notas de crédito de Compras
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de compra.
	
>>**Tipo**:boolean

>#### Notas de crédito de proyecto
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de proyecto.
	
>>**Tipo**:boolean

## Sección remito
![Ventana de configuración](Seccion-PackingSlip.png)

### Campos
>#### Remito
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de ventas.
	
>>**Tipo**:boolean

>#### Remito devolución
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de servicio.
	
>>**Tipo**:boolean

>#### Remito transferencia de inventario
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de compra.
	
>>**Tipo**:boolean

>#### Remito de proyecto
>>**Descripcion**: 
	Indica que puede ser usado en notas de crédito de proyecto.
	
>>**Tipo**:boolean