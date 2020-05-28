# LATAM Clase de comprobante
![Ventana de configuración](../../Imagenes/LATAM-VoucherClass-MainPage.PNG)

## Descripción
Se debe contar con un maestro que permita dar de alta los diferentes comprobantes con los que puede trabajar la compañía en relación con terceros. Ejemplo: Factura, Nota de Débito, etc. <br>
Además se utilizará para cargar comprobantes representantes de valores como ser Cheques de Terceros al Día y comprobantes representantes de transacciones de Tesorería como  Recibo u Orden de Pago. <br>
Esta venta permite configurar el comprobante así como el comportamiento de varios de sus campos y como se va a comportar los campos relacionados a la generación del numero de comprobante.

## Sección General
### Campos
***
>#### No.
>>**Descripción**: Este campo deberá ser completado manualmente por el usuario, identificando con un código al comprobante que se esté dando de alta. 
	
>>**Tipo**:Code[15]

>#### Descripción
>>**Descripción**: Este campo deberá ser completado manualmente por el usuario, ampliando con un detalle el código de comprobante que se esté dando de alta. 
	
>>**Tipo**:Text[100]

<!-- #### Descripción Legal 
**Descripción**: 
	
>>**Tipo**:Code[5]
-->

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

>>Ejemplo:   
Factura A ->  FCA<br>
Nota de Crédito E  -> NCE <br>
Documento de importación -> IM  <br>

	
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
>>**Descripción**: Caracter que permite introducir un separador al crear el [número de comprobante completo en la Extensión de documentos](../LATAM-DocumentExtension.md#numero-de-documento-completo). por ejemplo '-'. El separador va de la siguiente forma.

>>`[PREFIJO][SEPARADOR][PREFIJO PUNTO DE VENTAS][SEPARADOR][NUMERO DE COMPROBANTE]`
	
>>**Tipo**:Code[1]

>#### Copiar número de documento
>>**Descripción**: se utilizará para determinar si el Número de Documento completo será replicado en el campo nativo ‘Número de Documento’, en ‘Factura’  o bien en ambos. Siempre debe haber una opción seleccionada. Estará compuesto por las siguientes opciones: 

>>>* Ninguno: será guardado solamente en la tabla de Extensión de las transacciones sin replicar en ningún campo nativo de AX 

>>>* Número de Documento: si se encuentra marcada esta opción,  el número de Documento completo se guardará en el campo Nativo ‘Número de Documento’. 

>>>* Factura: si se encuentra marcada esta opción,  el número de Documento completo se guardará en el campo Nativo ‘Factura’. 

>>>* Ambos: se replicará en el campo ‘Numero de Documento’ y ‘Factura’ al mismo tiempo. 

>> Las opciones  en donde se encuentran ubicados estos campos varían según la transacción. En las EF de Tipificación de Transacciones, se indicará la ubicación exacta de cada campo. 

 
	
>>**Tipo**: Enum [LATAM CopyDocumentNum](../../Desarrollo/Enums/LATAM-CopyDocumentNum)

>#### Requiere CA
>>**Descripción**:  indica cuándo la carga de número de CAI/CAE se encuentra habilitada. En caso de no estar tildada  esta opción, los campos CAI/CAE y Fecha de Vencimiento en la solapa LA de los datos adicionales de Transacciones no se deberán visualizar. 

	
>>**Tipo**:Boolean

<!--
#### Requiere código de control
**Descripción**: 
	
>>**Tipo**:Boolean

>#### Tipo de código de control
>>**Descripción**: 
	
>>**Tipo**:Code[5]
-->
>#### Rótulo de concepto 1
>>**Descripción**: Los conceptos serán campos alfanuméricos que permitirán Guardar Información al momento de la carga de los Comprobantes. Su funcionamiento es igual que un definido de usuario. este campo define la etiqueta que usará. En la transacción, estos campos deberán visualizarse con  la etiqueta configurada y a su vez, deberán permitir el ingreso de un cierto valor. 
	
>>**Tipo**:Text[100]

>#### Rótulo de concepto 2
>>**Descripción**: Los conceptos serán campos alfanuméricos que permitirán Guardar Información al momento de la carga de los Comprobantes. Su funcionamiento es igual que un definido de usuario. este campo define la etiqueta que usará. En la transacción, estos campos deberán visualizarse con  la etiqueta configurada y a su vez, deberán permitir el ingreso de un cierto valor. 
	
>>**Tipo**:Text[100]

>#### Rótulo de concepto 3
>>**Descripción**: Los conceptos serán campos alfanuméricos que permitirán Guardar Información al momento de la carga de los Comprobantes. Su funcionamiento es igual que un definido de usuario. este campo define la etiqueta que usará. En la transacción, estos campos deberán visualizarse con  la etiqueta configurada y a su vez, deberán permitir el ingreso de un cierto valor. 
	
>>**Tipo**:Text[100]

>#### Nota 1
>>**Descripción**: Permitirá agregar información relacionada con el comprobante. No replicará en las ventanas transaccionales. 
	
>>**Tipo**:Text[250]

>#### Nota 2
>>**Descripción**: Permitirá agregar información relacionada con el comprobante. No replicará en las ventanas transaccionales. 
	
>>**Tipo**:Text[250]

>#### Nota 3
>>**Descripción**: Permitirá agregar información relacionada con el comprobante. No replicará en las ventanas transaccionales. 
	
>>**Tipo**:Text[250]

>#### Reporte
>>**Descripción**: 
Este campo permitirá  la asociación al comprobante de un ID de reporte en Reporting Services.

>>**Tipo**:Text[250]


<!--	
>>**Tipo**:Code[5]

>#### Tipo transacción banco
>>**Descripción**: 
	
>>**Tipo**:Code[5]

-->

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
### Descripción
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
### Descripción
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
Por otra parte si esta en `false` los campo [tipo de entrada](#tipo-asignacion) y [tipo de asignación]() en número de comprobante se setean en `manual` y `antes de contabilizar`
	
>>**Tipo**:boolean


>#### Longitud.
>>**Descripción**: Indica la longitud que debe tener el prefijo en [Punto de venta](../Maestros/LATAM-SalesPoint.md#prefijo-punto-de-venta). Esta validación se ejecuta en el campo [prefijo de punto de venta en extensión de documentos](../LATAM-DocumentExtension.md#prefijo). Este campo es editable cuando el campo tipo de entrada tiene el valor `automático`. Si tiene el valor  `manual` este campo es no editable y su valor se calcula en base a la longitud de la máscara.

>>**Editable**: Si esta en true el campo [Habilitado](#habilitado).

>>**Tipo**:boolean

>#### Máscara.
>>**Descripción**: Máscara para validar el prefijo de [Punto de venta](../Maestros/LATAM-SalesPoint.md).Determina la máscara y su tipo de verificación. Por ejemplo XXXXXXXX-X. La máscara deberá validar la  longitud configurada en el campo longitud. A su vez si se trata de letras, será alfanumérico. Si la máscara es numérica, sólo admitirá números.<br>
La configuración realizada en el Grupo ‘Máscara’ se validará al momento del ingreso de la transacción a partir de la carga del campo Comprobante.  

>>**Editable**: Si esta en true el campo [Habilitado](#habilitado).

>>**Tipo**:Text[250]

>#### Obligatorio.
>>**Descripción**: Indica que el punto de venta o el [prefijo de Punto de venta](../Maestros/LATAM-SalesPoint.md). es obligatorio.

>>**Editable**: Si esta en true el campo [Habilitado](#habilitado).

>>**Tipo**:boolean

>#### Tipo de entrada (Punto de venta).
>>**Descripción**: desplegable con las siguientes alternativas: 

>>* Manual: esta configuración influirá en los datos adicionales, cargados en [extensión de documentos](../LATAM-DocumentExtension.md), ya que si el punto de venta o el documento dice ‘manual’, podrá ser editado en  la misma transacción. 

>>* Automático: si se selecciona esta opción, en la ventana de extensión de documento, se deberá tener en cuenta el siguiente comportamiento: 

>>>* Punto de Venta: se deberá mostrar el desplegable con los Puntos de Venta disponibles en el Maestro de Puntos de Venta.  A su vez, si  la configuración del Punto de Venta por usuario se encuentra configurada, deberá ofrecer el punto de venta predeterminado de ese usuario.  

>>>* Documento: Si el Punto de Venta se encuentra habilitado y con la opción automático,  en el campo documento, sólo deberá dejar seleccionar ‘Automático’. Si se encuentra seleccionada la opción ‘Automático’, este campo NO podrá ser editado por el usuario en las ventanas  de Diarios y Facturas de Servicios. Estará grisado.  

Si el punto de venta no se encuentra habilitado o bien está habilitado y el campo esta con el valor ‘Manual’, el campo [tipo de entrada en ‘documento’](#tipo-de-entrada) deberá ser manual y no podrá cambiarse a ‘Automático’. Por otra parte si el valor es automático, el valor deo campo [tipo de entrada en ‘documento’](#tipo-de-entrada) deberá ser automático.

Además, si  la opción ‘Automático’  se encuentra seleccionado,  la columna 6° se habilitará.  

>>**Editable**: Si esta en true el campo [Habilitado](#habilitado).

>>**Tipo**:Enum "LATAM EntryType"

### Sub sección número de comprobante
***
>#### Obligatorio.
>>**Descripción**: indica que el campo [número de documento](../LATAM-DocumentExtension.md#numero-de-documento), es obligatorio.
	
>>**Tipo**:boolean

>#### Valida máscara.
>>**Descripción**: indica que el campo [número de documento](../LATAM-DocumentExtension.md#numero-de-documento), al ser ingresado tiene que cumplir la mascara definida en (#).
	
>>**Tipo**:boolean

>#### Longitud.
>>**Descripción**: Indica la longitud que debe tener el [número de comprobante](../LATAM-DocumentExtension.md#numero-de-documento).

>>**Editable**: Si esta en true el campo [Valida máscara](#valida-mascara).

>>**Tipo**:boolean

>#### Máscara.
>>**Descripción**: Máscara para validar el [número de comprobante](../LATAM-DocumentExtension.md#numero-de-documento). Determina la máscara y su tipo de verificación. Por ejemplo XXXXXXXX-X. La máscara deberá validar la  longitud configurada en el campo longitud. A su vez si se trata de letras, será alfanumérico. Si la máscara es numérica, sólo admitirá números.<br>
La configuración realizada en el Grupo ‘Máscara’ se validará al momento del ingreso de la transacción a partir de la carga del campo Comprobante.

>>**Tipo**:Text[250]

>#### Tipo de entrada
>>**Descripción**: desplegable con las siguientes alternativas: 

>>* Manual: esta configuración influirá en los datos adicionales, cargados en [extensión de documentos](../LATAM-DocumentExtension.md), ya que si dice ‘manual’, podrá ser editado en  la misma transacción. 

>>* Automático: si se selecciona esta opción, en la ventana de Diario o bien en la Factura de Servicio,  se deberá tener en cuenta el siguiente comportamiento: 

>>>* Documento: Si el Punto de Venta se encuentra habilitado y con la opción automático,  en el campo documento, sólo deberá dejar seleccionar ‘Automático’. Si se encuentra seleccionada la opción ‘Automático’, este campo NO podrá ser editado por el usuario en las ventanas  de Diarios y Facturas de Servicios. Estará grisado.  

>>Si el punto de venta no se encuentra habilitado o bien está habilitado y con la opción ‘Manual’, el campo ‘documento’ deberá ser manual y no podrá cambiarse a ‘Automático’. 

>>**Editable**: Si esta en true el campo [Habilitado](#habilitado).

>>**Tipo**:Enum

>#### Tipo asignación.
>>**Descripción**: Solo se habilitará para el campo Documento, en caso que se haya seleccionado ‘Automático’  en el campo [Tipo de entrada](#tipo-de-entrada). De lo contrario, aparecerá grisado. 

***
### Sección Medios de cobro/pago

####Descripción
En este grupo se ingresará toda la información relacionada con  aquellos Comprobantes, cuyo Tipo de Comprobante posee tildada la opción [Medio de Cobro/Pago](../Maestros/LATAM-VoucherClassType.md#medio-de-cobropago) en el maestro de [tipo clase de comprobante](../Maestros/LATAM-VoucherClassType.md).

>#### Tipo de medio de pago.
>>**Descripción**: 
	
>>Opciones: 

>>* Cartera de Terceros: Si se configura esta opción, este medio se administrará con Estados y se deberá guardar  en una tabla adicional especialmente creada para llevar su historia. Será utilizado en medios como  Cheques de Terceros, Tarjetas de Crédito/Debito, Prendas, Letras, Pagarés, etc. 
<br>Su funcionamiento requiere que  luego de haber sido  ingresado al sistema (por ejemplo cuando se recibe en una cobranza), para darlo de baja (egreso) se deba seleccionar. 
<br>Un ejemplo claro de este tipo de medios son los Cheques de Terceros, que ingresan a través de un cobro. Luego, al querer depositarlo o utilizarlo para pagar (Transacción de Egreso) se deberá seleccionar de un listado de medios con estas características (Cartera de terceros) que se encuentran en dicho estado. Al seleccionarlo en el egreso, se deberá adicionar la información del mismo y cambiar  a la tabla Histórica. 
<br>Para este tipo de Medio, se deberá trabajar con dos tablas propias de Localización Latam, de manera que en el  Ingreso se registre en una tabla que será la de Medios en cartera disponibles para usarse, y luego, cuando se lo utilice en una transacción para darlo de baja, se deberá eliminar de la tabla ‘Cartera’ para registrarse en la tabla ‘Histórico’, lo que significa que no podrá volver a utilizarse.
<br>La  tabla de ‘Cartera’ guardará los registros del Ingreso y a su vez le asignará un ID al registro y una Secuencia de Historia, por ejemplo ID: 1001 y Secuencia: 1. 
<br>Al tomar ese registro en un Egreso, se deberá ‘Eliminar’ de la Tabla de ‘cartera’ y crear el mismo registro en la tabla ‘Histórica’ adicionándole los datos del Egreso. 
<br>En caso que el valor o medio deba ser ‘Reingresado’ al sistema, al realizarse el ‘Reingreso’, deberá poder ser tomado de la Tabla de ‘Histórico’. 
<br>Una vez ‘Reingresado’ el Valor, se creará un nuevo registro en la tabla de ‘Cartera’, pero con el mismo ID  de la Transacción Original, para nuestro ejemplo, 1001. A su vez, la secuencia de Historia asignará el siguiente número correlativo, para nuestro ejemplo, 2. 
<br>Cuando el valor, se entregue nuevamente, seguirá con el procedimiento habitual: pasará a la tabla de histórico con el mismo ID y secuencia. De esta forma, en la tabla de histórico se podrán relacionar todas las transacciones de un Medio. 
<br>En los Diarios, este Tipo de Valor  generará una línea con el Tipo de Cuenta: Cliente. 

 
 
>>**Editable**: ver descripción del grupo [Sección Medios de cobro/pago](#descripcion_4).

>>**Tipo**:Enum [LATAM CPDPaymentMediaType](../../Desarrollo/Enums/LATAM-CPDPaymentMediaType)



-Banco: Este tipo estará  asociado a Medios como Débitos Bancarios, Acreditaciones Bancarias, Transferencias Bancarias, Efectivo y todo medio que afecte directamente a un Banco o Caja. 

Este  Tipo  de Medio no llevará Estado, sin embargo, habrá que asociarle datos adicionales al momento de la carga. 

Por Ejemplo, cuando se realice una transferencia Bancaria para pagarle a un sujeto, o un cliente nos realice un depósito Bancario o transferencia bancaria se deberá configurar el Medio como tipo de medio ‘Banco’, de manera de poder completar el número de depósito o transferencia, como también la fecha de la transacción.  

Al seleccionar como Tipo de Medio ‘Banco’  se deberá habilitar   un desplegable de las Cuentas Bancarias. Este campo NO será de carga Obligatoria, en el Maestro de Medios. Si se completa, al momento de seleccionar el medio en una transacción, la Cuenta Bancaria  se asignará de manera automática. 

En los Diarios Generarán una línea con el Tipo de Cuenta: Banco 

 

-Retención: Este tipo de medio, se utilizará para el ingreso de Retenciones, ya sean sufridas (las que nos realizan  nuestros clientes al pagarnos) como realizadas (las que realiza la compañía a sus proveedores). Al configurar una cuenta bancaria, con este tipo de medio, cuando se lo utilice en transacciones de Ingresos (Recibos) (saldo en el DEBE), el sistema solicitará cierta información asociada al medio. 

Lo mismo sucederá, si se encuentra en el Haber (Egreso).  

En los Diarios Generarán una línea con el Tipo de Cuenta: Banco. 

 

En este tipo de medio existe una salvedad: en el MAE de Tipos de Comprobante (Tab Documentos de AX) existe una configuración específica para los Medios de Cobro/Pago que determina que este sea el único  medio por asiento. Cuando esta configuración se encuentre realizada para un determinado Tipo de Comprobante y éste se asocie a un registro en el maestro de Comprobante, no se deberá poder seleccionar la opción Retención en el campo Tipo de medio de cobro/pago .  

En conclusión, no puede haber  un comprobante de Tipo Retención cuyo Tipo de Comprobante posea marcado el check de ‘Único MCP por asiento’ 

 

 

  

 

FormaForma 

 

 

 

-Valores Propios: Se utilizará  para  representar los Cheques Propios al Día y cualquier otro documento que emita la empresa, que no posea una fecha de Vencimiento. Estos  Medios, al igual que los valores del Tipo ‘Cartera de Terceros’,  se deberán guardar en la tabla ‘Histórico’. 

En caso que se encuentre seleccionada esta opción, se deberá generar una línea del tipo ‘Banco’ y como cuenta la cuenta bancaria seleccionada en el maestro del  medio. 

 

Cuando este medio se utilice en las acciones Emisión (Haber), se deberán completar los datos asociados al medio como datos adicionales y generar el número de cheque. Una línea en la tabla de ‘histórico’ se creará cuando  la transacción se registre. 

Cuando este medio se seleccione en la acción ‘Anulación’ (Debe), se habilitará el botón ‘selección de valores’ mostrando los documentos almacenados en la tabla de Histórico, que posean el mismo tipo. Una vez seleccionado el documento se deberá completar automáticamente los datos adicionales de la transacción original. 

Una nueva línea en la tabla  de histórico se creará, cuando esta transacción de registre. 

 

-Cartera propia: Se utilizará para distinguir los cheques Propios  Diferidos o cualquier otro documento que posea fecha de vencimiento.  

Estos  Medios, al igual que los valores del Tipo ‘Cartera de Terceros’,  se deberán guardar en la tabla de ‘Cartera’ e  ‘Histórico’. 

Al seleccionar un medio de este tipo, se deberá crear una línea del Tipo ‘Proveedor’ en las líneas del asiento, con la cuenta del proveedor que se ha seleccionado en la transacción. 

Este medio puede utilizarse en las siguientes acciones, según cual se trate, deberá comportarse: 

Si este tipo de medio se asocia a una acción de ‘Emisión’ (Haber), el usuario deberá completar los datos adicionales asociados a este medio. Luego se deberá generar el número de cheque. 

Al registrarse la transacción,  se deberá crear un nuevo registro en la tabla de cartera. 

Si este medio se utiliza en la acción ‘Devengamiento’ (Debe), se deberá habilitar el botón ‘Selección de valores’ con los documentos de este tipo que se encuentren en la tabla ‘Cartera’. Una vez seleccionado el medio, se deberán completar automáticamente los datos adicionales de la transacción original. 

Para este caso,  se deberá crear de manera automática la contrapartida del Tipo Banco, con la cuenta bancaria seleccionada en la línea del medio. 

Registrada esta transacción, se deberá  quitar el registro de la tabla de cartera y    crear en la tabla de ‘Histórico’. 

Si este medio se utiliza bajo una acción de ‘Anulación’, se deberá habilitar el Botón ‘selección de valores’, para poder  reversar los documentos de este tipo. 

 

Acción: Campo Opcional. Será  un grupo de  Checks Box  que permitirán indicar si el medio trabajará en: 

-Ingresos: Deberá permitir  tildarse sólo  medios de Tipo: Cartera de Terceros, Bancos, Retenciones. Los demás deberán estar grisados. 

-Egresos: Deberá permitir  tildarse sólo  medios de Tipo: Cartera de Terceros, Bancos, Retenciones. Los demás deberán estar grisados. 

-Reingresos: Deberá permitir  tildarse sólo  medios de Tipo: Cartera de Terceros. Los demás deberán estar grisados. 

-Emisión: deberá permitir  tildarse en Medios del Tipo: Valores Propios, Cartera Propia 

-Devengamiento: deberá permitirse solo en Medios del Tipo: Cartera Propia 

-Anulación: deberá permitirse sólo en medios del Tipo: Valores Propios, Cartera Propia. 

 

Perfil de Contabilización: Campo Obligatorio 

 

A cada medio se le podrá configurar un Perfil de Contabilización.  

Según el Tipo de Medio deberá habilitar: 

Cartera de Terceros: Se deberá visualizar el Perfil de Contabilización de Clientes.   Al momento de seleccionar este tipo de medio, se deberá reemplazar el perfil de la línea por  el Perfil del medio. 

Banco: a los Medios del  Tipo ‘Banco’, se le podrá asociar  una cuenta bancaria. Al generar una transacción y   tomar un medio cuyo tipo sea ‘Banco’,  la cuenta de banco se asociará de forma automática, tomando la cuenta contable configurada en la Cuenta Bancaria. El campo Perfil  de Contabilización, estará deshabilitado en este caso. 

Retenciones: posee el mismo Funcionamiento que los Medios del Tipo ‘Banco’. El campo Perfil  de Contabilización, estará deshabilitado en este caso. 

Valores Propios: a los Medios del  Tipo ‘valores propios’, se le podrá asociar  una cuenta bancaria. Al generar una transacción y   tomar un medio cuyo tipo sea ‘Valores Propios’,  la cuenta de banco se asociará de forma automática, tomando la cuenta contable configurada en la Cuenta Bancaria. El campo Perfil  de Contabilización, estará deshabilitado en este caso. 

Cartera Propia: se deberán visualizar los perfiles de contabilización de Proveedor. Al momento de seleccionar este tipo de medio, se deberá reemplazar el perfil de la línea por  el Perfil del medio. 

 

 

 

Moneda 

Permitirá seleccionar la moneda predeterminada  del medio.  

A su vez, deberá existir un campo Check box ‘Habilita cambio de Moneda’. Si el Check box se encuentra tildado, la moneda del medio podrá ser editada al momento de transaccionar en la ventana de Entrada de Valores. De ser así, deberá controlar que la Cuenta Bancaria asociada al medio (Si tuviera),  posea la misma  Moneda que la asociada al Valor, de lo contrario deberá impedir el cambio. 

Si el tilde no se encuentra marcado, no podrá modificarse la moneda del medio en la transacción.  

Check Box ‘Requiere Fecha Diferida’ 

Será un Check box que controle que la Fecha de Documento sea menor que la Fecha de Vencimiento. 

Esta validación se utilizará en aquellos comprobantes que representen valores diferidos como ser Cheques de Terceros Diferidos, Cheques Propios Diferidos, etc. 

Este campo se encontrará habilitado para todos  los Tipos de Valor. 

 

Grilla de Cuentas Bancarias 

Será una grilla en el Tab Medios de Cobro Pago con dos campos: 

Cuenta Bancaria: será un campo desplegable que ofrecerá los registros de cuentas  bancarias cargados en el formulario de Detalles de Cuentas Bancarias. 

Nombre: será la descripción de la cuenta Bancaria. Campo no editable. 

Validaciones: 

 

Esta grilla deberá estar habilitada cuando  el Tipo de Medio de Cobro/Pago sea  Banco, Retención, Valores Propios, Cartera Propia. 

En cualquiera de estos casos, se deberá  obligar a cargar en la grilla al menos una cuenta bancaria.  

El aviso  se deberá emitir al querer guardar, cambiar de Tab o cerrar la ventana. 

Al momento de la carga de la transacción, este campo ofrecerá de manera predeterminada la cuenta bancaria seleccionada en la grilla, en caso de haber una opción seleccionada. Si hay más de una no  completará con nada y ofrecerá en la selección las opciones ingresadas en la grilla. 

 

Solapa Nombres de Diario 

Aquí se podrá listar los Nombres de Diarios, en los cuales podrá seleccionarse este comprobante. Se permitirá asociar diarios, tanto a comprobantes de Tipo valor como otros comprobantes, como ser Factura. 

Esta solapa deberá Listar  un desplegables en donde se pueda seleccionar  Diarios desde el Maestro de Nombres de Diario. 

 

Los Diarios que se ofrecerán dependerán de:  

Comprobantes de Tipo Valor: 

Se deberá controlar que sólo permita seleccionar los diarios que comparten  Tipos de Valores y Acciones. 

Por ejemplo:  

En el Nombre de Diario ‘Ingresos de Cobros’ se ha configurado que el mismo sólo permite ‘Ingreso’. 

En el Medio de Cobro se ha permitido la acción de ‘Ingreso’ y ‘Reingreso’. 

Al seleccionar  en el Medio ‘Cheques de Clientes’, el Diario de Cobro,  sólo estará habilitada la opción ‘Ingreso’. 

 

Comprobantes No Valor: 

Deberá ofrecer todos los Journals. 

 

Como Opción deberá ofrecer  un  Botón ‘Agregar Todos’.  Si se presiona, el  comprobante podrá trabajar  con los diarios, dependiendo de lo siguiente: 

 

Comprobantes de Tipo Valor: Asignará todos los Nombres de Diario   cuya configuración de los Campos Tipo de Valor y Acción coincida con la configuración del Comprobante ‘Valor’ 

 

Comprobantes No Valor: Deberá asignar  todos los Journals disponibles. 

 

Si   no se presiona la  opción ‘Agregar Todos’, se deberá  seleccionar al menos un Diario. 

El  aviso de la  falta de asignación  de al menos un nombre de Diario se deberá realizar al momento de guardar el registro, cambiar de Tab,  o bien cerrar  la ventana. 

 

El botón ‘Borrar Todos’, quitará todos los Nombres de Diario asignados en la Grilla, independientemente del Tipo de Comprobante. 

 

 

Valores de Tipo Cartera de Terceros 

 

En caso de tratarse de un Medio de Cobro del ‘Tipo Cartera de Terceros’, se  deberán agregar 2 nuevas columnas: 

AWLAREASONSTART 

Label ES:   Estado Inicial 

Label EN:  Initial State      

Help al pie  ES:  Seleccione el estado inicial. 

Help al pie  EN:  Select the initial state. 

AWLAREASONEND 

Label ES:  Estado Final 

Label EN:  Final State 

Help al pie  ES:  Seleccione el estado final. 

Help al pie  EN:  Select the final state. 

 

Ambos campos tienen el mismo tipo que el campo REASON del maestro de Motivos (Reason Code). 

En ambos campos se implementara un LookUp al maestro de  Motivos / Reason Codes, mostrando únicamente aquellos  Motivos o Reason Codes que tengan marcado el Check que hemos agregado llamado  Cartera de Terceros. (Ver EF de Códigos de Motivos) 

 

 

 

NOTA:   Los campos de   Estado Inicial y Final     siempre deben ser editables si se trata de un Valor de Tipo Cartera de Terceros.   Y nunca deben ser editables (ni mostrarse las columnas) si se trata de otro tipo de Valor. 

 

Solapa Datos Adicionales 

 

Campos adicionales de Información requeridos por tipo: En esta sección se detallará para cada opción, los campos que deberán habilitarse cuando se registre una transacción parametrizada con cada tipo de medio. 

 

Esta ventana  tendrá las siguientes  columnas:  

En una columna desplegará todos los campos adicionales que se detallan a continuación. 

Conjunto  de Banco 

Origen del Cheque 

Datos del Firmante (se tratará de tres campos: Tipo de Documento, Número de Documento y Razón Social). Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Beneficiario 

Número de Cuenta del Titular 

Cuotas 

Importe Sujeto (Importe calculado)  

Base imponible  

Alícuota Efectiva (Alícuota  Aplicada)  

Base Acumulada 

Retención Acumulada 

Concepto 1 (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Concepto 2 (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Concepto 3(Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 1:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 2:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 3:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 4:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 5:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 6:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 7:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 8:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 9:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

Lista 10:   (Estos Datos deben poder configurarse y estar disponibles a pesar de que el comprobante NO  sea del  Tipo ‘Medio de cobro/Pago) 

 

Al lado de cada concepto deberá colocarse un desplegable con las siguientes opciones: 

-Deshabilitado: Para este medio, el campo se encontrará deshabilitado. 

-Habilitado: Para  este medio, el campo se encontrará habilitado, pero no será mandatorio. 

-Mandatorio: Para este medio, el campo se encontrará habilitado y a su vez será mandatorio. 

Este Dato permitirá definir si el Dato Adicional se mostrará para ser cargado en el medio y si es de ingreso obligatorio o no. 

Adicionalmente, en algunos campos se deberá permitir cargar una máscara, por si esta es requerida. Si el campo  de la máscara se encuentra vacío, no solicitará máscara. Si la misma se encuentra completa, por ejemplo XXXX-XXXXX, deberá solicitarla al cargar el campo en la transacción. El tipo de Verificación dependerá de los  campos utilizados para construir la máscara. Por ejemplo, si se han utilizado letras el campo será alfanumérico, en cambio, si se utilizan números, se tomará como numérico. 

Los datos Adicionales que tendrán esta información serán:  

-Número de Cuenta de Titular 

 

 

Comportamiento de Datos Adicionales por Tipo de Medio de Cobro/Pago 

 

-Cartera de Terceros: Cuando se utilice, en las transacciones, el medio que tenga el  Tipo ‘Cartera de Terceros’, si el importe se ingresa en el Debe (Ingreso), ya sea en un diario de cobro, en un diario de pago y en un Diario de contabilidad, el sistema deberá solicitar la carga  de la siguiente información: 

 

Conjunto de Bancos: El usuario deberá seleccionar en este campo el código de banco al que pertenece el medio que está entregando el cliente. Para ello se utilizará el campo estándar de AX conjunto de Banco. 

 

El ABM de este maestro se encuentra en BANCOS >>CONFIGURAR >> CONJUNTO DE BANCOS. 

 

 

De manera predeterminada, este tipo de medio debe ser Mandatorio, en la carga de la transacción. 

 

Origen del Valor: Este campo debe ser lista, y seleccionar entre dos valores posibles. Debe estar vacío y la opción ser seleccionada por el usuario. Este campo deberá agregarse ya que no existe dentro de AX estándar. 

•Propio del Cliente 

•Terceros 

 

Este campo, estará relacionado con los datos Id Firmante. En caso que se seleccione ‘Propio del cliente’, automáticamente se deberá completar los datos del firmante,  con el Tipo de documento (CUIT, DNI, etc.) y Razón Social,  asociados al código de cliente al que se está ingresando la Transacción. 

 

Sí, en cambio, se elige ‘Terceros’, los datos del firmante deberán estar vacíos para ser completados en la transacción. 

Ver campo ‘Datos Firmante’. 

De manera Predeterminada, este campo debe ser mandatorio. 

 

Número de Documento: Es un campo donde el usuario deberá ingresar el Número de Documento que representa al valor que está entregando el cliente. Por ejemplo, sí el cliente  está entregando un cheque, en este campo se deberá ingresar el número de cheque. Luego,  el dato que se complete en este nuevo campo de Localización de AX, deberá replicarse según lo configurado en el Tab General del Maestro de Comprobante. (Grupo Documento) y, en caso de los Diarios y Detalles de Orden de Compra, deberá tener en cuenta lo configurado como máscara. 

 

Datos del Firmante:  

En el caso de los medios cuyo tipo sean ‘Cartera de Terceros’ deberán completarse los Datos del Firmante. Estos campos de manera predeterminada deberán venir  como Mandatorios. Los datos de Firmante serán: 

-Tipo de Documento: en caso de que el Origen del Valor sea ‘Propio’ deberá completar el Tipo de Documento de acuerdo al Cliente en el cual se carga el Cobro. (Tomar el dato desde el ABM de Clientes- Solapa Latam). En caso contrario quedará libre para ser completado por el usuario que carga la transacción.  

-Número de Documento: En caso que el origen del valor sea ‘Propio’, deberá completar con el número de documento del cliente  asociado al cobro (Tomar el dato desde el ABM de Clientes- Solapa Latam). En caso que sea de terceros, deberá dejar en blanco para ser completado por el usuario. 

-Razón Social: si el Origen del valor es ‘propio’ deberá completarse con el Nombre del Cliente asociado al cobro. (Tomar el dato desde el ABM de Clientes- Nombre- Solapa General). De  lo contrario el campo deberá estar vacío para ser completado por el usuario. 

 

Fecha de Documento:  

Permitirá ingresar la fecha de emisión del Documento. Este campo deberá replicarse se replicará en los campos  nativos  Documento y Factura de la  línea, dependiendo de los configurado en el maestro del comprobante. 

 

 

Fecha de Vencimiento:  

Permitirá ingresar la fecha de vencimiento del Documento. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Vencimiento (LedgerJournalTrans_Due) de la línea del Asiento. Si este campo no se encuentra visualizable en la ventana de diario se deberá agregar. 

 

Botón Cuotas:  

No será un campo Mandatorio. Se utilizará para colocar la cantidad de cuotas en las cuales  estará dividido el valor.  Este campo no es nativo en AX por lo que se deberá crear. Al presionar el Botón cuotas se desplegará una ventana para cargar  información de las cuotas.  Sólo se encontrará habilitado en la ventana de Entrada de Valores. 

Esta ventana se describirá en la EF de Entrada de Valores. 

 

Número de Cuenta de Titular: Campo No obligatorio, se podrá utilizar para rellenar el número de cuenta corriente del cliente. Como este campo no existe en AX, se deberá crear un campo nuevo para tal Fin. 

Al momento de la transacción, deberá respetar lo configurado como Tipo de Verificación y máscara. 

 

En caso que el Tipo de Valor ‘Cartera de Terceros’ se mueva  en el Haber (Egreso), se deberá  habilitar un botón ‘Selección   de Valores’, en las ventanas de Diario de Pago/Cobro (Cuentas por Pagar), Diarios de Pago/Cobro (Cuentas por Cobrar) y Diario general (Contabilidad General). Dicho botón desplegará una ventana que mostrará las líneas que se encuentran en la tabla de ‘Cartera’. 

Para el caso que  este tipo de Medios se encuentre en el Debe (Reingreso), también deberá estar habilitado el botón ‘Selección de Valores’. Esta vez, el mismo desplegará una ventana mostrando las líneas de la tabla de valores ‘Histórica’. 

En el caso de los Ingresos, el Botón ‘Selección de Valores’ NO deberá estar Habilitado. 

-Banco: Cuando se seleccione este tipo de medios en el Debe o en el Haber (Ingreso o Egreso), se deberá habilitar los campos que se describen a continuación.  

Se recuerda que cuando se mueva este tipo de medio, se deberá crear en las líneas de Asiento una nueva línea del Tipo ‘Banco’.  

 

Cuenta Bancaria: 

De manera predeterminada se ofrecerá la cuenta bancaria seleccionada en la grilla del Tab General de maestro de Comprobante, en caso de ser única, de lo contrario deberá ofrecer en el desplegable todas las opciones configuradas en la grilla. Cuando este campo se complete, deberá replicarse en el campo ‘Cuenta’ de la línea de Banco creada. De manera predeterminada, éste será  un campo mandatorio en el maestro de Valores con este tipo. 

 

Fecha de Documento:  

Permitirá ingresar la fecha de emisión de este valor. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Documento (DocumentDate) de la línea del asiento. 

Fecha de Vencimiento:  

Permitirá ingresar la fecha de vencimiento del Valor. Este campo deberá replicarse al momento de generar el cobro en el campo (LedgerJournalTrans_Due) de la línea del Asiento 

 

Número de Documento: Es el campo en  donde el usuario deberá ingresar el número de transacción. Luego,  el dato que se complete en este nuevo campo de Localización de AX, deberá replicarse según lo configurado en el Tab General del Maestro de Comprobante. (Grupo Documento) y, en caso de los Diarios y Detalles de Orden de Compra, deberá tener en cuenta lo configurado como máscara. 

 

Datos del Firmante:  

En el caso de los medios cuyo tipo sean ‘cartera de Terceros’ deberán completarse los Datos del Firmante. Estos campos de manera predeterminada No serán Mandatorios. 

-Tipo de Documento: deberá completarse el Tipo de Documento de acuerdo al Cliente en el cual se carga el Cobro. (Tomar el dato desde el ABM de Clientes- Solapa Latam). Podrá ser modificado por el usuario. 

-Numero de Documento: deberá completarse con el número de documento del cliente  asociado al cobro (Tomar el dato desde el ABM de Clientes- Solapa Latam). Podrá ser modificado por el usuario. 

-Razón Social: deberá completarse con el Nombre del Cliente asociado al cobro. (Tomar el dato desde el ABM de Clientes- Nombre- Solapa General). Podrá ser modificado por el usuario.7 

 

-Beneficiario 

Campo No Obligatorio, en el maestro de Valores de manera predeterminada. En la transacción deberá completarse con el Nombre del Proveedor relacionado al Pago. Podrá ser Editado por el usuario. 

Para el caso de imprimirse los cheques de terceros por AX tomará el  beneficiario desde este campo. 

 

 

 

-Retención: 

Se recuerda que este tipo de Medio representará los certificados de retención dados por el cliente al momento del Pago o  Entregados al Proveedor. 

Cuando este tipo de medio se mueva por el Debe (Ingreso), se deberán solicitar los siguientes campos: 

 

Cuenta Bancaria: De manera predeterminada se ofrecerá la cuenta bancaria seleccionada en la grilla del Tab General de maestro de Comprobante, en caso de ser única, de lo contrario deberá ofrecer en el desplegable todas las opciones configuradas en la grilla. Cuando este campo se complete, deberá replicarse en el campo ‘Cuenta’ de la línea de Banco creada. De manera predeterminada, éste será  un campo mandatorio en el maestro de Valores con este tipo. 

 

Fecha de Documento:  

Será un campo Obligatorio de manera predeterminada. Permitirá ingresar la fecha de emisión del certificado de retención. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Documento (DocumentDate) de la línea del asiento. Será un campo mandatorio en el maestro de valores, de manera predeterminada. 

 

Número de Documento: Será el campo donde el usuario deberá ingresar el número de certificado de Retención entregado  por el cliente. Luego,  el dato que se complete en este nuevo campo de Localización de AX, deberá replicarse según lo configurado en el Tab General del Maestro de Comprobante. (Grupo Documento) y, en caso de los Diarios y Detalles de Orden de Compra, deberá tener en cuenta lo configurado como máscara. 

Cuando este Tipo de Medio se mueva por el Haber (Egreso) se deberá completar la siguiente información: 

Número de Documento 

Fecha de Documento 

Importe Sujeto  

Base imponible  

Alícuota Efectiva  

Base Acumulada 

Retención Acumulada 

Conceptos 1..3 (Según lo configurado en el tab General del Maestro del Comprobante. 

 

 

-Valores Propios:   los campos que se habilitarán en  todos los medios que posean este tipo serán: 

 

Cuenta Bancaria: 

De manera predeterminada se ofrecerá la cuenta bancaria seleccionada en la grilla del Tab General de maestro de Comprobante, en caso de ser única, de lo contrario deberá ofrecer en el desplegable todas las opciones configuradas en la grilla. Cuando este campo se complete, deberá replicarse en el campo ‘Cuenta’ de la línea de Banco creada. De manera predeterminada, éste será  un campo mandatorio en el maestro de Valores con este tipo. 

 

Fecha de Documento:  

Será un campo Obligatorio de manera predeterminada. Permitirá ingresar la fecha de emisión de este valor. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Documento (DocumentDate) de la línea del Medio. 

 

Fecha de vencimiento 

 No será  un campo Obligatorio de manera predeterminada. Permitirá ingresar la fecha de vencimiento del Valor. Este campo deberá replicarse al momento de generar el cobro en el campo (LedgerJournalTrans_Due) de la línea del Asiento. 

 

 

Beneficiario 

Campo Obligatorio, de manera predeterminada en el Medio. En la transacción deberá completarse con el Nombre del Proveedor relacionado al Pago. Podrá ser Editado por el usuario. 

Para el caso de imprimirse los cheques de terceros por AX tomará el  beneficiario desde este campo. 

 

Número de Documento 

Representará el número de cheque emitido. En el caso de los Valores Propios, al generarse el número de cheque, se deberá replicar en los campos que correspondan (Numero de Documento/Factura) según lo configurado en el maestro de comprobante. 

 

Cuando el valor, cuyo tipo es ’Valores Propios’ se mueva por el Haber (Emisión), se deberá crear una línea de Banco. 

Cuando  un Medio tipo  ‘Valores Propios’, se mueve en el Debe (Anulación), la ventana de ‘Selección de Valores’, deberá habilitarse, mostrando los valores que se encuentran en la tabla de Histórico en la ventana de Entrada de Valores. 

El botón ‘Seleccionar valores’ sólo mostrará los Medios  o Valores que  tengan el Tipo ‘Valores Propios’. A su vez, si en la tabla de histórico hay más de una línea con el mismo  ID de transacción, sólo deberá mostrar la línea cuya   secuencia de Historia sea mayor.  

Este movimiento creará una línea del tipo Banco, con la cuenta bancaria  del movimiento original. 

Estos casos serán explicados detalladamente en  la EF del Formulario Entrada de Valores. 

-Cartera Propia:   los campos que se habilitarán en  todos los medios que posean este tipo serán: 

 

Cuenta Bancaria: 

Será el ABM de cuentas bancarias que nativamente ofrece el sistema. Cuando este campo se complete, deberá replicarse en el campo ‘Cuenta’ de la línea de Banco creada. De manera predeterminada, éste será  un campo mandatorio en el maestro de Valores con este tipo. 

 

 

Fecha de Documento:  

Será un campo Obligatorio de manera predeterminada. Permitirá ingresar la fecha de emisión de este valor. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Documento (DocumentDate) de la línea del Medio. 

 

Fecha de Vencimiento:  

No será  un campo Obligatorio de manera predeterminada. Permitirá ingresar la fecha de vencimiento del Valor. Este campo deberá replicarse al momento de generar el cobro en el campo Fecha de Vencimiento (LedgerJournalTrans_Due) de la línea del Medio. 

 

Beneficiario 

Campo Obligatorio, de manera predeterminada en el Medio. En la transacción deberá completarse con el Nombre del Proveedor relacionado al Pago. Podrá ser Editado por el usuario. 

Para el caso de imprimirse los cheques de terceros por AX tomará el  beneficiario desde este campo. 

Número de Documento 

Representará el número de cheque emitido. En el caso de la Cartera  Propia, al generarse el número de cheque, se deberá replicar en los campos que correspondan (Numero de Documento/Factura) según lo configurado en el maestro de comprobante. 

 

 

Cuando  un Medio tipo  ‘Cartera Propia’,  se mueve en el Debe (Devengamiento), la ventana de ‘Selección de Valores’, deberá habilitarse, mostrando los valores que se encuentran en la tabla de Cartera. 

Este movimiento deberá crear una línea del Tipo Proveedores (en el Debe) con la cuenta correspondiente al proveedor de la Transacción Original. 

Por otro lado, de manera automática se deberá colocar como contrapartida,   ‘Banco’, con la cuenta bancaria seleccionada en el valor. 

Cuando el Medio, cuyo Tipo es ‘Cartera Propia’, se mueve en el Haber (Emisión), el usuario deberá completar los datos adicionales del valor y generar el número de cheque 

Cuando el Medio, cuyo Tipo es ‘Cartera Propia’, se mueve en el Haber (Anulación), deberá habilitarse el botón ‘Selección de Valores’, que mostrará los Valores que se encuentran en la tabla de   Cartera e Histórico, según se trate de  la anulación de un cheque propio que fue entregado pero no debitado en el banco (Cartera) o bien se haya debitado en el Banco (Histórico).  

Si se selecciona un valor de esta tabla, todos los datos adicionales al valor se deberán cargar de manera automática. Esto permitirá realizar el Reingreso del Valor. 

Si en la tabla de histórico, hay más de una línea con el mismo  ID de transacción, sólo deberá mostrar la línea cuya   secuencia de Historia sea mayor. 

Estos casos serán explicados detalladamente en  la EF del Formulario Entrada de Valores. 

 

Botón Comprobantes en Punto de Venta. 

Será un botón que abra la ventana de Comprobante en Punto de Venta para que el usuario pueda ingresar o consultar los registros existentes. 

No deberá hacer ningún filtro al abrir esta ventana. 

 

Tab Dimensiones 

 

Debe existir la posibilidad de asociar las dimensiones financieras disponibles  a  un comprobante, de manera tal que al  seleccionar el comprobante en la transacción, se  predeterminen las dimensiones  en esa línea afectada por el comprobante. 

 

Botón ‘Aplicativo’ 

 

Código Aplicativo para el tipo de documento 

Cada comprobante definido en el sistema (Factura A, Factura B, Factura C, etc) puede tener una codificación distinta en distintos aplicativos de distintos organismos.    Por ejemplo puede tener un código para los aplicativos de Ingresos Brutos Provincia de Buenos Aires, que para los aplicativos de AFIP RG1361, o AFIP City Compras. 

Es por eso que para cada ID de Comprobante debemos poder asociar distintos valores para distintos Id Aplicativo y en algunos casos alguna información necesaria para el aplicativo. 

Se sugiere una grilla con los siguientes campos: 

a.look-up al maestro de aplicativos 

b. nombre/descripción del aplicativo (solo lectura) 

c.código que se le da a este Comprobante para ese aplicativo.  Es obligatorio. 

d.código letra: es el código de letra que lleva este comprobante para este aplicativo.  (sólo se utilizará en algunos aplicativos).   Es optativo. 

Nota: si se opta por una solución con una única tabla para todos los códigos de aplicativos para todas las entidades el campo Código Letra solo tendría uso en  Código Aplicativo de Comprobante.  Con lo cual se podría utilizar como un campo  genérico 1 que para esta relación tiene este significado pero para otra relación podría tener otro significado.

PENDIENTE MCP
medio-de-cobro pago
Si el Tipo de Comprobante  posee tildada la opción ‘Medio de Cobro/Pago’ el tab ‘Documentos de AX’, en el Maestro de Tipo de Documento;  los Tab ‘Medio de Cobro/Pago’, ‘Nombres de Diario’, se encontrarán habilitadas, de lo contrario no se visualizarán. 