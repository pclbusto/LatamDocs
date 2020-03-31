#LATAM Extensión orden de ventas
![Extensión parte pagina](MainPage.png)
##Descripción
Extensión a orden de ventas. Este documento puede tener hasta 3 extensiones. La primera extensión refiere a datos del contribuyente. Las otras dos extensiones dependen del tipo de documento a generar cuando se contabilice. Este documento puede generar un remito, una factura sobre lo remitido o puede remitir y facturar al mismo tiempo. Ahora dependiendo de del tipo de contabilización que se haga serán las extensiones que pueden llegar a ser requeridas. Si solo se va a remitir va a aparecer la extensión para remitir. Si se va a factura solo la extensión para facturar y si va a realizar ambas aparecen las dos extensiones ademas de la extensión que refiere a datos del contribuyente.
Respecto a la extensión de datos del contribuyente, la funcionalidad es tener un conjunto de datos que pueda ser replicado a la sección de contribuyente de lao las extensiones del documento a generar. Para esto al momento de seleccionar el comprobante en la sección correspondiente, si el comprobante tiene marcada la opción de [detalla contribuyente](../../Maestros/LATAM-VoucherClass/LATAM-VoucherClass.md#detalla-contribuyente), se trata de recuperar información de dos lugares: 

1. Se revisa si se tiene cargado los datos de contribuyente en la extensión de la cabecera de la orden. De existir información copia esta info a la sección de contribuyente en la que se este trabajando (Remito o factura).
2. Si no hay información en el paso anterior se busca la información en la entidad asociada al documento. En este caso en la [extensión del cliente](../../Extensiones/LATAM-Customer/LATAM-Customer.md)
El circuito para esto sería cargar datos en la sección de contribuyente de la orden 
###Campos

>####Tipo de contribuyente
>>** Descripción **: 
	
>>**Tipo**:Code

>####Grupo tipo de cuenta
>>** Descripcion **: 
	Id. del grupo de tipo cuenta a la que pertenece el cliente. Solo puede ser un grupo de tipo cuenta cuyo tipo sea cliente. Ver [tipo en grupo tipo cuenta](../../Maestros/LATAM-AccountTypeGroup/LATAM-AccountTypeGroup.md#tipo-de-cuenta).
	
>>**Tipo**:Entero