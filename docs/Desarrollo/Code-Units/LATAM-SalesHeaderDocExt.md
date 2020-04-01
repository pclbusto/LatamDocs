#LATAM SalesHeaderDocExt

##Descripción
Esta CU es la encargada de toda la funcionalidades de la entidad [Document Extension](../../../LATAM-DocumentExtension/LATAM-DocumentExtension.md). Posiblemente se una a la CU [Document Extension](Desarrollo/Code-Units/LATAM-Document-Extension/LATAM-Document-Extension/).

## procedimientos
***
>####check_exist_and_create
>>**Parametros:**

>>**Descripcion**: 
	
>####DeleteExtension

>>**Parametros:**

>>**Descripción**:
	

>####GetAccountGroupFromWorkDocument

>>**Parametros:** 
>>> * **"No." _Code[20]_** Número del documento. Tanto para ventas como para compras la clave para el documento es No. y "Document type" con este valor mas el tipo vamos a recuperar la entidad que participa en el documento correspondaiente.
>>> * **"Document Type" _Option_**: indica el tipo de documento. Tanto para ventas como para compras la clave para el documento es No. y "Document type" con este valor mas el numerador vamos a recuperar la entidad que participa en el documento correspondaiente.
>>> * **LATAMDocumentExtensionType _Enum ["LATAM DocumentExtensionType"](../../../Desarrollo/Enums/LATAM-DocumentExtensionType/LATAM-DocumentExtensionType.md)_**: Este parámetro permite saber de donde tomar el id de la entidad. Si este parámetro tiene algún valore relacionado a ventas sabemos que lo que tenemos que buscar el un cliente. Por el contrario si es algun valor relacionado a compras este procedimiento busca el grupo de proveedor.

>>**Retorna**:
>>>* LATAMAccountTypeGroupId **(Code [20])**

>>**Descripción**:Cada documento tiene una entidad (cliente, proveedor, etc), cada una de estas entidades tiene asoaciada un [grupo de tipo de cuenta](../../../Maestros/LATAM-AccountTypeGroup/LATAM-AccountTypeGroup.md), en ese grupo uno configura lista de comprobantes a las cuales tiene acceso. Este procedimiento retorna el Id de grupo asociado a la entidad que participe en el documento.

>####GetAccountGroupCustomer

>>**Parametros:**

>>**Retorna**:
>>>* LATAMAccountTypeGroupId **(Code [20])**

>>**Descripción**: 
	Retorna el id de grupo asociado al cliente.

>####GetAccountGroupVendor

>>**Parametros:**

>>**Descripción**: 



***
