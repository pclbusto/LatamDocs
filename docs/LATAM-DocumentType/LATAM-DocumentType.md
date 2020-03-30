# LATAM Tipo Documento
![Ventana de configuración](LATAM-DocumentType-MainPage.png)
## Descripción
Maestro de tipos de documentos. Permite especificar algunas características para los número de documentos ingresados por ejemplo formato, si usa o no algoritmo de verificación (CUIT, RUC), si es o no un documento del exterior, estado o país.

## Sección General
### Campos

>#### No.
>>**Descripción**: 
	Habilita o deshabilita la localización. Si este campo esta en falso el código de la localización no debería ejecutarse. Esto implica extensiones a páginas o código que ejecuta en puntos de integración.
	
>>**Tipo**:Code

## Sección configuración
### Campos
>#### Descripción
>>**Descripción**: 
	Cantidad de caracteres que permite el campo letra de comprobante de la entidad [letra de comprobante](../LATAM-LATAMVoucherClassLetter/LATAM-LATAMVoucherClassLetter.md) letra de comprobante.
	
>>**Tipo**:Entero

>#### Verifica método
>>**Descripción**: 
	Si tiene implementado un metodo de verificación, ejecuta dicho método para verificar si el número de documento ingresado es correcto.
	
>>**Tipo**:Entero

>#### Máscara
>>**Descripción**: 
	Cantidad de caracteres que permite el campo prefijo de clase de comprobante de la entidad clase de comprobante.
	
>>**Tipo**:Entero

>#### Longitud máscara
>>**Descripción**: 
	Cantidad maxima de caracteres que permite la máscara.
	
>>**Tipo**:Entero

>#### Valida máscara
>>**Descripción**: 
	Indica si hay que validar o no la mascara. Si esta deshabilitado los campos longitud máscara y máscara deben estar deshabilitados.
	
>>**Tipo**:boolean

>#### Tipo documento país
>>**Descripción**: 
	Indica que este tipo de documento es de país. En la ventana de configuración de tipo de contribuyente ()
	
>>**Tipo**:boolean

>#### Tipo documento estado
>>**Descripción**: 
	Indica que este tipo de documento es estado.
	
>>**Tipo**:boolean

>#### Tipo documento exterior
>>**Descripción**: 
	Indica que este tipo de documento es del exterior.
	
>>**Tipo**:boolean