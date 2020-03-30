#LATAM Sales Post Suscribers
##Descripción
Esta CU tiene todos los event suscribers referidos al proceso de posting de ventas de la CU 80 Sales-Post. 

##Eventos suscriptos

###OnBeforePostGLAndCustomer
>#### Parámetros

var SalesHeader: Record "Sales Header";
var TempInvoicePostBuffer: Record "Invoice Post. Buffer" temporary;
var CustLedgerEntry: Record "Cust. Ledger Entry";
CommitIsSuppressed: Boolean;
PreviewMode: Boolean;
var GenJnlPostLine: Codeunit "Gen. Jnl.-Post Line";
var IsHandled: Boolean


>#### Descripción

En este evento creamos la extensión para la Cutomer ledger. Básicamente copiamos la info de la extensión del documento de ventas contabilizado. Esta copia se hace para poder tener los datos en la ledger de customer y no tener que hacer el join con las tablas de históricos de documentos. Al tener una extensión a la tabla "Cust. Ledger Entry" solo vamos cargar los datos en la extensión y dejar que el proceso de posting haga el resto, de esta manera vamos a evitar hacer actualizaciones a la "Cust. Ledger Entry"de forma innecesaria. 