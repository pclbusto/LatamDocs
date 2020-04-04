# LATAM Tax Payer Type
![Ventana de configuración de tipo de contribuyente](../Imagenes/LATAM-TaxPayerType-MainPage.PNG)
## Descripción
Ventana de configuración de tipo de contribuyente.

## Sección general
![Ventana de configuración de tipo de contribuyente](../Imagenes/LATAM-TaxPayerType-Seccion-General.PNG)

### Campos

>#### No.
>>**Descripción**: 
Identificador único de tipo contribuyente.

>>**Tipo**:Code

>#### Descripción.
>>**Descripción**: 
Breve descripción.

>>**Tipo**:Text

>#### Valida código de autorización
>>**Descripción**: 
Solo tiene validez si esta clase de contribuyente se usa con un proveedor. Este flag indica que los documentos de este proveedor van a requerir un CA al momento de ser cargados.

>>**Tipo**:Boolean

>#### Contribuyente exterior
>>**Descripción**: 
Indica que es un contribuyente del exterior. Este flag impacta en los documentos a los cuales tiene acceso en la [sección tipo documento contribuyente](#seccion-tipo-documento-contribuyente). Si este flag esta en `true` entonces el lookup solo mostrará documentos que tengan el flag [Tipo documento exterior](LATAM-DocumentType.md#tipo-documento-exterior) en `true`.

>>**Tipo**:Boolean

>#### Contribuyente interno
>>**Descripción**: 
FALTA
>>**Tipo**:Boolean

>#### País de radicación requerido
>>**Descripción**: 
Para toda entidad que use una clase de contribuyente que tenga este flag en `true` hace que el campo país de radicación sea requerido. Por ejemplo en [país de radicación](../Extensiones/LATAM-Customer.md#pais-de-radicacion) del cliente.

>>**Tipo**:Boolean

>#### Documento estado requerido
>>**Descripción**: 
Para toda entidad que use una clase de contribuyente que tenga este flag en `true` hace que el campo inscripto en jurisdicción sea requerido. Por ejemplo en [inscripto en jurisdicción](../Extensiones/LATAM-Customer.md#pais-de-radicacion) del cliente.

>>**Tipo**:Boolean

>#### Juridiscción requerida
>>**Descripción**: 

>>**Tipo**:Boolean

>#### Documento estado requerido
>>**Descripción**: 

>>**Tipo**:Boolean

## Sección tipo documento contribuyente
### Campos
>#### Tipo documento
>>**Descripción**: 
	
	
>>**Tipo**:Code
>#### Descripción
>>**Descripción**: 
	
	
>>**Tipo**:text