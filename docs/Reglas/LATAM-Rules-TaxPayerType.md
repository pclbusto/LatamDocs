# Comportamiento fijados por tipo de contribuyente

##Descripción
Esta sección define el comportamiento de los campos:

* País de radicación

* Tipo documento país

* N° documento país

* Inscripto en jurisdicción

* Tipo documento estado

* N° documento estado

 que se tienen en las extensiones de [Cliente](../Extensiones/LATAM-Customer.md), [Proveedor](../Extensiones/LATAM-Vendor.md), [Compañía](../Extensiones/LATAM-CompanyInformation.md) y [Banco](../Extensiones/LATAM-Bank.md), al momento de seleccionar un tipo de contribuyente.

### Campos
>#### Tipo de Contribuyente
>>**Descripción**:

>>Debe requerirse como campo obligatorio la identificación de **Tipo Contribuyente**. EJ. Responsable Inscripto. <br>
El usuario, deberá seleccionar del maestro [Tipo de contribuyente](../Maestros/LATAM-TaxPayerType.md), el que corresponda a la entidad que se esta trabajando.<br>
De acuerdo a la configuración del Tipo de contribuyente, se deberá habilitar el campo **Tipo documento país** y **Tipo documento estado**, para que el usuario seleccione el que corresponde para la entidad y así posteriormente poder completar los campos **N° documento país** y **N° documento estado** con sus correspondientes formatos. <br>

>#### Radicado en país
>>**Descripción**:
	Indica el País donde se encuentra radicado el cliente. Ej.  Argentina.  El comportamiento de este campo será determinado a partir de lo configurado en el Tipo de Contribuyente  como [Documento país requerido](../Maestros/LATAM-TaxPayerType.md#documento-pais-requerido). <br>
	Solo se podrá seleccionar los Países que coincidan en el campo Exterior con el campo Exterior del Tipo de Contribuyente seleccionado.  Es decir si el Tipo de Contribuyente tiene configurado Exterior = SI, solo se deberá permitir seleccionar los Países que tengan configurado Exterior = SI. ver [Contribuyente exterior](../Maestros/LATAM-TaxPayerType.md#contribuyente-exterior)<br>
	Esta configuración permitirá junto con el tipo de contribuyente (seleccionado anteriormente), filtrar los tipos de documento País permitidos para la entidad. De esta manera,  el usuario tendrá solo la posibilidad de configurar los que estén disponibles luego del filtro entre el tipo de documento País, configurado para el seleccionado en el campo Radicado en y el tipo de documento País, configurado para el tipo de contribuyente.  <br>
	En caso que el País seleccionado, sea Nacional, es decir que no se encuentre configurado como de Exterior, se debería asociar el Estado en el cual está inscripto la entidad (Campo: Jurisdicción Inscripta) que permitirá filtrar los tipos de documento Estado permitidos para el contribuyente y Estado seleccionado. 

>#### Tipo documento país
>>**Descripción**:
Podrán ser seleccionados solo aquellos que cumplan estas condiciones:

>>* [Tipo Documento](../Maestros/LATAM-TaxPayerType.md#tipo-documento) asociados al [Tipo Contribuyente](../Maestros/LATAM-TaxPayerType.md) seleccionado. ver [Sección tipo documento contribuyente](../Maestros/LATAM-TaxPayerType.md#seccion-tipo-documento-contribuyente)

>>* Los tipos de documentos deben tener el campo [Tipo documento país](../Maestros/LATAM-DocumentType.md#tipo-documento-pais) en `true`

>>* Tipo Documento deben estar en el País en el que está radicado el cliente. 

>>Ahora si aplicamos las tres reglas de arriba y como resultado se tiene un único **Tipo de documento** se deberá seleccionar automáticamente. Si el campo **Radicado en** y/o el **Tipo Contribuyente** no están seleccionados, no se deberá mostrar ningún valor posible.  Si alguno de estos campos cambia se deberá borrar el campo **Tipo documento país** y si la nueva intersección da un elemento, se deberá seleccionar automáticamente. 

>>El comportamiento del campo es determinado por el campo [documento país requerido](../Maestros/LATAM-TaxPayerType.md#documento-pais-requerido)

>#### N° documento país
>>**Descripción**:
Se habilitará una vez seleccionado el tipo de documento país, teniendo en cuenta el tipo de contribuyente asociado al registro ID de Cliente que se está queriendo registrar.<br>
Si el tipo de documento tiene marcado [Validar máscara](../Maestros/LATAM-DocumentType.md#validar-mascara) o [Verifica método](../Maestros/LATAM-DocumentType.md#verifica-metodo). Este valor debe ser validado.
>>El comportamiento del campo es determinado por el campo [documento país requerido](../Maestros/LATAM-TaxPayerType.md#documento-estado-requerido)

>#### Tipo de documento estado
>>**Descripción**:
Podrán ser seleccionados aquellos que cumplan estas condiciones: 

>>* [Tipo Documento](../Maestros/LATAM-TaxPayerType.md#tipo-documento) asociados al [Tipo Contribuyente](../Maestros/LATAM-TaxPayerType.md) seleccionado. ver [Sección tipo documento contribuyente](../Maestros/LATAM-TaxPayerType.md#seccion-tipo-documento-contribuyente)

>>* Los tipos de documentos deben tener el campo [Tipo documento estado](../Maestros/LATAM-DocumentType.md#tipo-documento-estado) en `true`

>>* Tipo Documento deben estar en el estado en el que está inscripto el cliente. 

Ahora si aplicamos las tres reglas de arriba y como resultado se tiene un único **Tipo de documento** se deberá seleccionar automáticamente. Si el campo **Jurisdicción Inscripta en** y/o el **Tipo Contribuyente** no están seleccionados, no se deberá mostrar ningún valor posible.  Si alguno de estos campos cambia se deberá borrar el campo **Tipo de documento estado** y si la nueva intersección da un elemento, se deberá seleccionar automáticamente.<br>
En caso que el registro de cliente no cuente con todos los datos  requeridos en función al Tipo de Contribuyente  o bien no se seleccione el Tipo de Contribuyente; el registro de cliente no se podrá activar, ya que el campo checkbox **Inactivar** debe estar marcado. A su vez, el campo checkbox **Inactivar**  no se debería poder editar hasta tanto se cumplan los requisitos  de alta del cliente. 

>#### Inscripto en jurisdicción
>>**Descripción**:
Solo debería seleccionar un código de Estado (Provincia) perteneciente al país de radicación. De estar en blanco país de radicación no debe mostrar datos el lookup.

>>El comportamiento del campo es determinado por el campo [documento estado requerido](../Maestros/LATAM-TaxPayerType.md#documento-estado-requerido)

Este campo será obligatorio dependiendo de lo configurado en  el Tipo de Contribuyente (seleccionado anteriormente) en el campo ‘Jurisdicción Inscripta Obligatorio’. 

Si el contribuyente no es interno ni del exterior la ‘Jurisdicción Inscripta’ debería ser obligatoria. 

Si el contribuyente es  Interno, la ‘Jurisdicción Inscripta’ no debería ser obligatoria. 

Si el contribuyente es del exterior la ‘Jurisdicción Inscripta’ podría ser obligatoria o no. 

Solo se mostrará los Estados que pertenecen al País en el que está radicado el cliente.  Si ese país cambia, se deberá vaciar el campo Estado. 

Esta configuración, junto con el tipo de contribuyente seleccionado, permitirá dejar solo disponibles como ‘Tipo de Documento Estado’ a los que surjan de la conjunción entre lo configurado en el valor colocado como **Jurisdicción Inscripta** y **Tipo de contribuyente**. 

 

 

Tipo de documento Estado: Este campo deberá habilitarse una vez configurado, el tipo de contribuyente. EJ. IIBB BA. 

Debe ser un campo obligatorio, sí el tipo de contribuyente configurado es del tipo Nacional (se configuró NO en el campo Exterior en el maestro de tipo de contribuyente).  

Sí el tipo de contribuyente es del Exterior, no será obligatorio, seleccionar el Tipo de documento Estado e ingresar el Número de identificación Estado.  

En este campo, AX, solo permitirá seleccionar entre los tipos de documento Estado que coincidan entre lo configurado para el Estado donde se encuentra inscripto el cliente, y los configurados para el tipo de contribuyente parametrizado que tienen configurado Tipo Documento Estado=SI. 

 Sí de este filtro, se obtiene un solo tipo de documento Estado, entonces será AX, el que completará automáticamente el campo **Tipo de documento Estado**.  

En caso contrario, se permitirá al usuario, seleccionar el tipo de documento Estado entre los que sean coincidentes entre Tipo de contribuyente y Estado de Jurisdicción del cliente. 

Ejemplo: Al  tipo de contribuyente Responsable Inscripto, se le ha configurado como tipo de documento admitido, el CUIT, IIBB BS AS, IIBB Córdoba, IIBB Capital Federal. A su vez los tipos de documento de IIBB fueron parametrizados como tipo de documento Estado. En cambio el CUIT, fue configurado como Tipo de documento País. 

Al Estado Buenos Aires se lo configuró con el Tipo de documento Estado, IIBB BS AS, y CUIT-IB. 

Por lo tanto, sí al Cliente, se le configura la jurisdicción inscripta  en **Buenos Aires** y el Tipo de contribuyente, **Responsable Inscripto**, el campo Tipo de documento Estado, deberá completarse automáticamente con el valor IIBB BS AS, ya que es el único que se encontraría disponible entre la intersección de los tipos de documentos configurados en el Responsable Inscripto y en la jurisdicción Inscripta Buenos Aires. Una vez que se ha seleccionado o configurado automáticamente este campo, se deberá completar el Número de Identificación Estado. 

 

Número de identificación Estado: Se habilitará para los ID de Cliente, una vez seleccionado el tipo de documento Estado, y el tipo de contribuyente parametrizado.  

 Este número deberá ser obligatorio dependiendo de la configuración realizada en el Tipo de Contribuyente. 

Si el tipo de contribuyente  no es interno ni del exterior, el ‘Número de Identificación Estado’ deberá ser Obligatorio. 

Si el tipo de contribuyente es interno, el ‘Número de Identificación de Estado’ no debería ser obligatorio. 

Si el Tipo de Contribuyente es Externo  el campo podría ser obligatorio o no. 

Este número deberá validar con la máscara configurada en Tipo Documento. 