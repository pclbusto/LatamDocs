# LATAM Clase de comprobante
![Ventana de configuración](../../Imagenes/LATAM-VoucherClass-MainPage.PNG)

## Descripción
Se debe contar con un maestro que permita dar de alta los diferentes comprobantes con los que puede trabajar la compañía en relación con terceros. Ejemplo: Factura, Nota de Débito, etc. <br>
Además se utilizará para cargar comprobantes representantes de valores como ser Cheques de Terceros al Día y comprobantes representantes de transacciones de Tesorería como  Recibo u Orden de Pago. <br>
Esta venta permite configurar el comprobante así como el comportamiento de varios de sus campos y como se va a comportar los campos relacionados a la generacion del numero de comprobante.

## Sección General
### Campos
***
>#### No.
>>**Descripción**: Este campo deberá ser completado manualmente por el usuario, identificando con un código al comprobante que se esté dando de alta. 
	
>>**Tipo**:Code[15]

>#### Descripción
>>**Descripción**: Este campo deberá ser completado manualmente por el usuario, ampliando con un detalle el código de comprobante que se esté dando de alta. 
	
>>**Tipo**:Text[100]

>#### Descripción Legal
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Tipo Clase Comprobantes
>>**Descripción**: id tipo clase de comprobante. Indica que comportamiento va a tener este comprobante, el cual esta supeditado a lo configurado en el [tipo clase comprobante](LATAM-VoucherClassType.md).

>>**Tipo**:Code[15]

>#### Letra
>>**Descripción**: El usuario deberá seleccionar de un campo look-up las letras de comprobante disponibles del maestro de [Letra Comprobante](../Maestros/LATAM-VoucherClassLetter.md), la que identifica al código de comprobante que se está configurando (A, B, E, etc.). 
NOTA: A  efectos de la configuración de los comprobantes con Tipo ‘medio de Cobro/Pago, se creará una letra ‘Sin letra’ que no poseerá prefijo. 
	
>>**Tipo**:Code[15]

>#### Prefijo
>>**Descripción**: Cadena de caracteres que forma parte del cálculo del [número de comprobante completo](../LATAM-DocumentExtension.md#numero-de-documento-completo). Este prefijo es formado por el [prefijo del tipo de comprobante](LATAM-VoucherClassType.md#prefijo) y el [prefijo de la letra](../Maestros/LATAM-VoucherClassLetter.md#prefijo). 
Este campo, debe poder ser visualizado pero no modificable por el usuario. Sí los prefijos de Letra de comprobante y/o Tipo de comprobante, se encontraran vacíos, debería completarse en este campo con los espacios en blanco. 

Ejemplo:   

Factura A ->  FCA 

Nota de Crédito E  -> NCE 

Documento de importación -> IM  

	
>>**Tipo**:Text[5]

>#### Inactivo
>>**Descripción**: Campo check box. Permitirá inactivar un comprobante que no se utilice más. Si el comprobante se encuentra utilizado en alguna transacción no se podrá eliminar, por lo que este tilde permitirá que no sea seleccionado. 
	
>>**Tipo**:Boolean

>#### Forzar ...
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Cálculo de retenciones
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Separador
>>**Descripción**: Caracter que permite introducir un separador al crear el [número de comprobante completo en la Extensión de documentos](../LATAM-DocumentExtension.md#numero-de-documento-completo). por ejemplo '-'.
	
>>**Tipo**:Code[5]

>#### Copiar número de documento
>>**Descripción**: se utilizará para determinar si el Número de Documento completo será replicado en el campo nativo ‘Número de Documento’, en ‘Factura’  o bien en ambos. Siempre debe haber una opción seleccionada. Estará compuesto por las siguientes opciones: 

* Ninguno: será guardado solamente en la tabla de Extensión de las transacciones sin replicar en ningún campo nativo de AX 

* Número de Documento: si se encuentra marcada esta opción,  el número de Documento completo se guardará en el campo Nativo ‘Número de Documento’. 

* Factura: si se encuentra marcada esta opción,  el número de Documento completo se guardará en el campo Nativo ‘Factura’. 

* Ambos: se replicará en el campo ‘Numero de Documento’ y ‘Factura’ al mismo tiempo. 

Las opciones  en donde se encuentran ubicados estos campos varían según la transacción. En las EF de Tipificación de Transacciones, se indicará la ubicación exacta de cada campo. 

 
	
>>**Tipo**:Code[5]

>#### Requiere CA
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Requiere código de control
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Tipo de código de control
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Rótulo de concepto 1
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Rótulo de concepto 2
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Rótulo de concepto 3
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Reporte
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Tipo transacción banco
>>**Descripción**: 
	
>>**Tipo**:Code[5]

>#### Detalla contribuyente
>>**Descripción**:
Si este campo esta marcado, cambia el comportamiento a requerido de los campos en el [grupo de contribuyente](../Maestros/LATAM-VoucherClass.md#grupo-contribuyente) en la [sección de datos adicionales](../Maestros/LATAM-VoucherClass.md#seccion-datos-adicionales) en la entidad comprobante  
	
>>**Tipo**:boolean

>#### Incluye impuestos
>>**Descripción**: 
	
>>**Tipo**:Code[5]
***
## Sección Datos Adicionales
![Ventana de configuración](../../Imagenes/LATAM-VoucherClass-AdditionalData.PNG)
## Descripción
Configuración de campos adicionales. Esta sección permite configurar el comportamiento de los campos adicionales, los cuales aparecen en el formulario de [Extensión de Documentos](../LATAM-DocumentExtension.md). Están agrupados por secciones que son las mismas que tiene esta sección. Los comportamientos pueden ser:

* **Deshabilitado:** El campo aparece deshabilitado.
* **Habilitado:** El campo aparece como editable.
* **Requerido:** El campo aparece como editable y requerido.  

### Campos
***
>#### Comportamiento grupo banco.
>>**Descripción**: 
	
>>**Tipo**:Code[15]
>#### Grupo contribuyente
>>######	Tipo contribuyente
>>>**Descripción**: 
Permite administrar el comportamiento de los campos en el grupo [contribuyente en la página extensión de documentos](../LATAM-DocumentExtension.md#seccion-contribuyentes). 
>>**Tipo**:Code[15]
***
## Sección Máscara Documento
![Ventana de configuración](../../Imagenes/LATAM-VoucherClass-DocumentMask.PNG)
## Descripción
Configuración de máscaras para el punto de venta y el comprobante. Cuando se usa el comprobante en la ventana [Extensión de Documentos](../LATAM-DocumentExtension.md). Se disparan una series de comportamientos referidos al número de comprobante y punto de venta. Esta sección se sub divide a su vez por las entidades mencionadas anteriormente:

* Cuenta GL
* Cliente
* Proveedor
* Banco 
* Activo Fijo

cada una de estas secciones a su vez tiene dos secciones mas que son punto de venta y número de comprobante, pero el comportamiento que se describe se aplica a cada una de las secciones de las entidades.


### Sub sección punto de ventas
***
>#### Habilitado.
>>**Descripción**: Habilita o no el uso de punto de venta. Si este campo esta en falso en la ventana de extensión de documento el punto de venta está deshabilitado, además de esto los campos obligatorio, longitud, máscara y entrada están deshabilitado. Si está en true el campo punto de venta estará  habilitado en la extensión de documento y se habilitan los campos obligatorio, longitud, máscara y entrada.
	
>>**Tipo**:boolean


>#### Longitud.
>>**Descripción**: Indica la longitud que debe tener el prefijo en [Punto de venta](../Maestros/LATAM-SalesPoint.md#prefijo-punto-de-venta). Esta validación se ejecuta en el campo [prefijo de punto de venta en extensión de documentos](../LATAM-DocumentExtension.md#prefijo)

>>**Habilitado**: Si esta en true el campo Habilitado.

>>**Tipo**:boolean

>#### Obligatorio.
>>**Descripción**: Indica que el punto de venta o el [prefijo de Punto de venta](../Maestros/LATAM-SalesPoint.md). es obligatorio.

>>**Habilitado**: Si esta en true el campo Habilitado.

>>**Tipo**:boolean

>#### Máscara.
>>**Descripción**: Mascara para validar el prefijo de [Punto de venta](../Maestros/LATAM-SalesPoint.md).

>>**Habilitado**: Si esta en true el campo Habilitado.

>>**Tipo**:boolean
***


PENDIENTE MCP
medio-de-cobropago
Si el Tipo de Comprobante  posee tildada la opción ‘Medio de Cobro/Pago’ el tab ‘Documentos de AX’, en el Maestro de Tipo de Documento;  los Tab ‘Medio de Cobro/Pago’, ‘Nombres de Diario’, se encontrarán habilitadas, de lo contrario no se visualizarán. 