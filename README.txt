Abrir terminal en modo administrador 
Ingresar el siguiente comando:

"C:\Program Files\AR System\User\aruser.exe" /RegServer

En la carpeta G:\CRC-OPERATIONS\Back Office Consultas\PRUEBAS MACROS\PruebasMacros\Configuracion
se encuentra un archivo datime. dll hay que copiarlo a nuestra maquina local puede ser en escritorio o documentos

y luego copiarla a la siguiente ruta con permisos de administrador:

C:\Windows\System32

y vamos a ejecutar los siguientes comandos en nuestra terminal.

regsvr32 datime.dll
regsvr32 scrrun.dll
regsvr32 olepro32.dll

Dependiendo la version de Visual Basic que tengamos instalada en nuestra computadora vamos a ejecutar el comando correspondiente a la version
Si no sabemos que version tenemos podemos ejecutar ambos, uno nos dara un error de registro que no afecta ninguna funcionalidad.
Si tenemos ambas versiones, los dos registros seran exitosos:

regsvr32  "C:\Program Files\Common Files\microsoft shared\VBA\VBA6\VBE6.DLL"
regsvr32  "C:\Program Files\Common Files\microsoft shared\VBA\VBA7\VBE7.DLL"

Por último debemos asegurarnos que la carpeta de nombre Attachmate se encuentre en la ruta C:\Program Files si no encontramos esta carpeta podemos copiar la version que se encuentra en la siguiente ruta:
G:\CRC-OPERATIONS\Back Office Consultas\PRUEBAS MACROS\PruebasMacros\Configuracion

Con esta configuración previa las macros funcionaran correctamente.

- Si no funcionan en nuestra Macro vamos a la pestaña de Developer. 
Si no se encuentra esta pestaña vamos a la opcion 
File > Options > Customize Ribbon 
En la segunda columna marcamos la opción Developer

En la opcion Developer damos click en la primera opcion 
Visual Basic 

Cuando se abra Visual Basic For Applications 

Vamos a la opcion
Tools> Referencias

Si la Referencia ARUSER esta precedida por MISSING: 

Seleccionamos esta referencia, luego Browse para buscarla 

La referencia esta en la siguiente ruta:

C:\Program Files\AR System\User\ARUSER.tlb

Damos click en OK y podemos cerrar el programa 