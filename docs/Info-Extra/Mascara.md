# Definición de Máscara

Símbolos permitidos en la configuración de Mascaras.
 
 


|Símbolo	|descripción	|Ejemplos de mascara	|Ejemplos validos de entrada	|Salida|
------------|---------------|-----------------------|-------------------------------|------|
|X	|Representa un carácter Alfa numérico.	|XX	|W3, 44, TT, 3R	 | |
|Y	|Alfanumérico variable. Este carácter es un carácter comodín. El usuario al ingresar una cadena puede omitir ingresar números o letras en las posiciones donde están las Y.<br>Solo se pueden ingresar al principio de la cadena que representa la máscara. No se puede armar una máscara  de solo Y.  A la derecha de las Y debe haber al  menos una X, A o 9.<br>Este carácter no representa un espacio en blanco representa un vacío.|YYXX<br>YXX9<br>YYY9<br>Y9X9|	1W, 11R,RR71,1_TT(error)<br>RR1,TG8,GF1,RR11,1111<br>1,OIU1,T5<br>1F1,R1R1,4F6| |
|A|	Solo letras. No es de longitud variable.|	AA|FG||	  
||	|	A|F||	 
||	|	AAA|GYH||	
|9| Carácter numérico fijo. cada **9** implica un caracter numérico en el documento que use esta mascara|99|15|
|9||999|195|
|9||9999|111|error falta un caracter|
|0|	Carácter numérico variable. Este carácter es un carácter comodín. El usuario al ingresar una cadena puede omitir ingresar números en las posiciones donde están los 0.<br>No se puede armar una máscara  de solo 0.  A la derecha de los 0 debe haber al menos una X, A o 9.|000X|F,1G,546T|
|||009|1,5,6,123,541,125||
|||0AX9|1T00, T00, TT1||
|-|Representa un -|XX-XX|TR-EW||
|||XX-A9|RR-T1, TG-Y6||
|Sin símbolo|Si la cadena comienza con Y o 0 indica que la  modificación que sufra la cadena de entrada por autocompletado no será retornada.|YYXX|GTT|GTT|
|||009|34,67,886|34,67,886|
|||099X|123T,5436,99C|123T,5436,99C|
|||0X9AAA|T8ERT,765EWR|T8ERT,765EWR|
|@|Indica que la modificación que sufra la cadena de entrada por auto completado será retornado. Solo puede ir seguido de 0. En el caso de usar el símbolo Y va a dar error. No forma parte de la longitud de la mascara este caracter|@YYXX esto es incorrecto||
|||@009|3,45,234|003,045,234|
|||@099X|3C,45F,123F|Error, 045F,123F|
|||@0X9AAA|44HHH, R4TTT|044HHH,0R4TTT|

 
**Campo longitud:** tanto en documento como en comprobante no va a ser editable. Y se calcula en base a la máscara. Salvo el caso de numeración automática para comprobante en este caso se deja editar la longitud. 

**Longitud Máxima:** Al cargar una máscara sea en documentos o comprobantes tenemos un campo longitud asociado a la máscara. En el caso de que la máscara use  0 o Y, el campo longitud informa cuantos caracteres pueden ser ingresados como máximo. 

**Longitud Mínima:** una máscara puede iniciar con Y y 0. Sin embargo debe terminar con X, A o 9. Estos símbolos implican que  debe ir si o si un carácter alfanumérico. La longitud mínima de una cadena es la sub cadena formada por X, A o 0. Por ejemplo para la cadena &0X9AAA la longitud mínima es 5 mientras que la máxima es 6. Para la cadena YYXX la longitud máxima es 4 y la mínima 2.

**Validación de máscara respecto a longitud:** además que una máscara cumpla con los símbolos definidos para su validación. Una cadena que cumpla con la máscara debe tener una longitud comprendida entra la longitud mínima y máxima. 

**Autocompletar:** El proceso de validación de mascara internamente para longitud variable (mascaras que comienzan con YYYY o 000) convierte la cadena de ingreso a una cadena intermedia antes de hacer la validación final. En el caso de Y la cadena se autocompleta con espacios blancos a izquierda en el caso de 0 autocompleta con 0 a izquierda. Por ejemplo para una máscara 0000099 si ingresamos el valor 15 el valor intermedio resultante es 0000015, para el valor 54689 el valor resultante es 0054689. Básicamente lo que hace es completar con ceros a la izquierda hasta alcanzar la longitud de la máscara en esta caso 7. En el caso de Y vamos a usar el carácter “-“ para representar el espacio blanco. Para una máscara YYYYXX. Si ingresamos el valor  GT el valor intermedio será ----GT. Para el valor HYTG el valor intermedio será –HYTG.
Un requerimiento que surgió de esto fue que en algunos casos se pudiese recuperara este valor intermedio y en otros no. Por esta razón el símbolo @ permite recuperar el valor intermedio. Pero solo aplica para cadena que empiecen con 0, cadenas como por ejemplo YYYYXX van a retornar la parte alfanumérica nada más, no completa con vacíos. Esto se debe a que el formato del campo GP elimina los espacios en blanco a izquierda.

**Máscara avanzada:** surge de AX, pero en el mail que dio origen a este concepto no está claro a que se refiere. En AX el concepto de mascara avanzada  se refiere a poder editar el patrón que usa SQL para poder validar la máscara. GP no tiene esa opción por lo cual el concepto de mascara avanzada no tiene sentido. Sin embargo en el mismo mail hace referencia a poder recuperar el valor intermedio que usa el proceso de autocompletado.  
Por limitaciones tecnológicas GP no permite la edición de la máscara en forma de patrón. 
Para la máscara 00XXAA el patrón de esta mascara es [0-9][0-9][ ,a-z,A-Z][ ,a-z,A-Z][a-z,A-Z][a-z,A-Z]


Los símbolos @ y & no forman parte de la longitud de la cadena. Es decir que para una máscara &0000999AA la longitud es 9 y no 10. El símbolo “-“ también forma parte de la longitud de la máscara. Para simplificación de escritura de la máscara el símbolo & se omite. Es decir una máscara &YYYXXAA, es equivalente a YYYXXAA. Podrá ser escrita de las dos formas indicando solo que se desea validar y no usar el concepto autocompletar.

**IMAGEN DE TIPO DE DOCUMENTO**
 
 
Solo vamos a tener valida mascara Si/No. La opción Si va a validar la máscara. El proceso de validación retornara valido o no. El poder retornar el valor intermedio queda ahora en la configuración de la máscara  mediante el uso del símbolo @. No Validar no verifica. No permite el ingreso de mascara.
 
Con respecto a Número de Comprobante hay algunas cosas para aclarar.
 
Cuando la entrada de la máscara en clase de comprobante es automática

**IMAGEN DE MASCARA EN VOUCHER CLASS**
 
Es sistema no permite la edición de la misma. Solo muestra una máscara numérica que representa la longitud deseada de la misma. Esto es porque esta secuencia es de autoincremento y es necesario una cadena numérica para el funcionamiento de incremento.
En el caso de entrada manual el sistema permite el ingreso de una máscara con los símbolos especificado en la tabla 1. 


 **IMAGEN DE MASCARA EN VOUCHER CLASS**
 
Configuración de mascara en Opciones de clases de comprobante

El cuadro a continuación describe toda situación que puede surgir cuando se configura una máscara de clase de comprobante. 

|Punto de venta habilitado|Punto de venta Entada|Numero de comprobante Obligatorio|Numero de comprobante Validar mascara|Descripción comportamiento|
|-------------------------|---------------------|---------------------------------|-------------------------------------|--------------------------|
|True|Manual|True|True|La entrada en número de comprobante es manual. La longitud debe ser mayor que 0 y la máscara debe ser obligatoria. La longitud debe estar no editable y se calcula en base a la máscara.|
|True|Manual|True|False|La entrada en número de comprobante es manual. El campo máscara está deshabilitado y longitud también. Significa que tienen que ingresar algo, cuya longitud debe estar entre 1 y 12, sin validar longitud o máscara.|			
|True|Manual|False|True|La entrada en número de comprobante es manual. La longitud puede ser 0 y la máscara debe ser obligatoria. La longitud debe estar no editable y se calcula en base a la máscara. En este caso si el usuario no ingresa nada es correcto. Si ingresa algo debe ser validado por la máscara.|
|True|Manual|False|False|Los campos longitud y mascara están vacíos y deshabilitados.<br>No hay validación. Ni por longitud ni por máscara. Esto permite no ingresar nada en el campo.|
|True|Automático|True|True|La entrada es automática en número de comprobante. Es obligatorio es decir que la long tiene que ser mayor 0.<br>El flag Validar mascara debe estar en true y no puede ser editado y mascara tampoco. Se auto calcula como una máscara numérica de la longitud especificada en el campo longitud.|
|True|Automático|True|False|Estado inválido|
|True|Automático|False|True|Estado inválido|
|True|Automático|FalseFalse|Estado inválido|
|False|Deshabilitado|True|True|La entrada en número de comprobante es manual. La longitud debe ser mayor que 0 y la máscara debe ser obligatoria. La longitud debe estar no editable y se calcula en base a la máscara.|
|False|Deshabilitado|True|False|La entrada en número de comprobante es manual. El campo máscara está deshabilitado y longitud también. Significa que tienen que ingresar algo, cuya longitud debe estar entre 1 y 12, sin validar longitud o máscara.|
|False|Deshabilitado|False|True|La entrada en número de comprobante es manual. La longitud puede ser 0 y la máscara debe ser obligatoria. La longitud debe estar deshabilitada y se calcula en base a la máscara. En este caso si el usuario no ingresa nada es correcto. Si ingresa algo debe ser validado por la máscara.|
|False|Deshabilitado|False|False|Los campos longitud y mascara están vacíos y deshabilitados.<br>No hay validación. Ni por longitud ni por máscara. Esto permite no ingresar nada en el campo. 



