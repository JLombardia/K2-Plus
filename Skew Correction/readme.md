#### English
- Edit the file _printer.cfg_ and add in the includes section the line:
 
     ````
     [include macro___led_extrusor.cfg]
     ````

- Copy the file _macro___led_extrusor.cfg_ to the configuration folder.


You can turn on and off from the macro buttons _NOZZLE_LED_ON_ and _NOZZLE_LED_OFF_

#### Spanish
La llamada _skew correction_ corrige la proporcionalidad entre los ejes x e y. El valor se puede obtener cuando hacemos un ajuste de tamaño de estos ejes con impresiones como la _califlor o flor de cali_, tambien llamado _calistar_ que es el que yo recomiendo. Lo tenemos disponible en el proyecto https://github.com/dirtdigger/fleur_de_cali que tiene la web implementada para ejecutarse localmente en printables por el autor del proyecto. En https://www.printables.com/model/778188-calistar-parametric-open-source-alternative-to-cal descargamos un comprimido en cuyo interior tenemos los modelos y un fichero index.htm que al abrir nos permite meter los datos que midamos en la pieza impresa obteniendo finalmente el valor de contracción/expansión del filamento, buscando la mayor precisión en tamaño, y obtenemos el valor de skew.  
Para evitar tener que resetear la impresora tras cambiar los datos para que los cargue en memoria, trabajamos con variables y estas se cargan en cada impresión, lo que nos evita este reinicio tras cualquier cambio.  

  
- Edita el fichero _printer.cfg_ y añade en la seccion de los _includes_ inicial la línea:
 
     ````
     [include macro___set_skew_correction.cfg]
     ````

- En el mismos archivo _printer.cfg_ iremos al final del mismo. Justo antes de todos los cambios que introduce la K2 iniciandose por #*# debemos de escribir:

     ````
     [save_variables]
     # Fichero en el que guardaremos nuestras variables personalizadas.
     filename: ~/printer_data/config/variables.cfg

     [skew_correction]
     # Bloque creado para el ajuste de skew
     
     ````
- Crearemos, si no existe, un fichero vacío llamado _variables.cfg_ en la carpeta de configuarciones.

- Copia el fichero _macro___set_skew_correction.cfg_ a la carpeta de configuración.

- Edita _gcode_macro.cfg_ y  bBusca la sección _[gcode_macro START_PRINT]_. Al principio de la misma, en la primera linea, activamos las variables insertando la linea  

     ````
     variable_prepare: 0
     ````

Y en la misma sección, al final de la misma, despues de la última linea, introducimos:

     ````
     SET_MY_SKEW
     ````

A partir de dicho momento disponemos de un nuevo boton de macro llamado _SET_USER_SKEW_ que tiene una flechita hacia abajo. Esto indica que se nos va a desplegar para introducir valores. En ese desplegable podemos introducir los valores calculados, se almacenaran en _variables.cfg_ y se cargarán esos valores automáticamente en cada impresión.

