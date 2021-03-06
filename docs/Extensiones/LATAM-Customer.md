# LATAM Extension Customer
![Ventana de configuración](../Imagenes/LATAM-Customer-Extension-MainPage.PNG)
## Descripción
Extensión a los clientes de Business Central.

### Campos

>#### Tipo de contribuyente
>>**Descripción**: 
	ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)

>>**Tipo**:Code[15]

>#### País de radicación

>>**Descripción**: 
	Id de país que indica donde esta radicado el cliente. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)

	
>>**Tipo**:Code[10]

>#### Tipo documento país

>>**Descripción**: 
	Id a tipo de documento. Solo pueden cargarse tipos de documentos que tenga el flag [tipo documento país](../Maestros/LATAM-DocumentType.md#tipo-documento-pais) en `true`. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)
	
>>**Tipo**:Text[15]

>#### N° documento país
	
>>**Descripción**: 
	Número de documento del contribuyente. Si el tipo de documento tiene marcado [Validar máscara](../Maestros/LATAM-DocumentType.md#validar-mascara) o [Verifica método](../Maestros/LATAM-DocumentType.md#verifica-metodo). Este valor debe ser validado. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)
	
>>**Tipo**:Text[30]

>#### Inscripto en jurisdicción

>>**Descripción**: 
	Id [Estado](../Maestros/LATAM-State.md) en que está inscripto. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)
	
>>**Tipo**:Code[10]

>#### Tipo documento estado

>>**Descripción**: 
	Id a tipo de documento. Solo pueden cargarse tipos de documentos que tenga el flag [tipo documento estado](../Maestros/LATAM-DocumentType.md#tipo-documento-estado) en `true`. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)
	
>>**Tipo**:Text[15]

>#### N° documento estado
	
>>**Descripción**: 
	Número de documento del contribuyente. Si el tipo de documento tiene marcado [Validar máscara](../Maestros/LATAM-DocumentType.md#validar-mascara) o [Verifica método](../Maestros/LATAM-DocumentType.md#verifica-metodo). Este valor debe ser validado. Ver [Comportamiento fijados por tipo de contribuyente](../Reglas/LATAM-Rules-TaxPayerType.md)
	
>>**Tipo**:Text[30]
	
>#### Grupo de cliente
>>**Descripción**: 
	Id. del [tipo en grupo tipo cuenta](../Maestros/LATAM-AccountTypeGroup.md) a la que pertenece el cliente. Solo puede ser un grupo tipo cuenta cuyo tipo sea cliente. Ver [tipo en grupo tipo cuenta](../Maestros/LATAM-AccountTypeGroup.md#tipo-de-cuenta)
	
>>**Tipo**:Code[20]

>#### Concepto 1
>>**Descripción**: 
	Campo de texto libre. Puede tener el significado que el usuario decida darle mediante la etiqueta definida en la [sección definido usuario cliente, concepto 1](../LATAM-Setup/LATAM-Setup.md#etiqueta-concepto-1). El valor que se ingrese en esa configuración determina el rótulo que va a tener en esta ventana.
	
>>**Tipo**:Text[250]

>#### Concepto 2
>>**Descripción**: 
	Mismo comportamiento que el campo concepto 1.
	
>>**Tipo**:Text[250]

>#### Concepto 3
>>**Descripción**: 
	Mismo comportamiento que el campo concepto 1.
	
>>**Tipo**:Text[250]

>#### Nota 1
>>**Descripción**: 
	Mismo comportamiento que el campo concepto 1.
	
>>**Tipo**:Text[250]

>#### Nota 2
>>**Descripción**: 
	Mismo comportamiento que el campo concepto 1.
	
>>**Tipo**:Text[250]

>#### Nota 3
>>**Descripción**: 
	Mismo comportamiento que el campo concepto 1.
	
>>**Tipo**:Text[250]