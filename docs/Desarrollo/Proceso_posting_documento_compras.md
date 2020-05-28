#Proceso de posting




OnBeforePostInvPostBuffer: en este procedimiento creamos las extensiones para diario. Se hace en este punto porque se detecta que un poco mas adelante el proceso del documento finaliza con lo cual la extensión del documento ya no existe. El código consiste en crear la extensión al diario que se esta creando y luego copiar la extensión latam del documento a la extensión del diario.
**Nota**: Solo se crean extensiones de diarios para tipos de documentos Proveedor o cliente.
