#LATAM Purchase Post Suscribers

##Descripción
Esta CU tiene todos los event suscribers referidos al proceso de posting de ventas de la CU 80 Sales-Post. 

##Eventos suscriptos


###OnAfterCheckMandatoryFields
>#### Parámetros

var PurchaseHeader: Record "Purchase Header"; 
CommitIsSupressed: Boolean)

>#### Descripción

En este evento se valida los requeridos y reglas del negocio que corresponda. 
Se hace el reemplazo de los numeradores que corresponda. 

|Documento|sub documentos|campo con numeración LATAM|
|---------|--------------|:--------------------------:|
|Factura compras|No tiene|Vendor Invoice No.|
|Nota de crédito|No tiene|Vendor Cr. Memo No.|
|Orden de compra|remito|Vendor Shipment No.|
|Orden de compra|factura|Vendor Invoice No.|
|Orden de devolución de compra|remito devolución|Return Shipment No.|
|Orden de devolución de compra|nota de credito|Vendor Cr. Memo No.|

<br>
[] Pendiente el calculo de la numeración cuando es automática y al momento de contabilizar.


###OnAfterPurchInvHeaderInsert

>#### Descripción

Copia los datos de [Extensión de documento](../../LATAM-DocumentExtension.md) a la extensión de 
