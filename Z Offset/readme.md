#### English
You may have noticed that the Z-Offset adjustment is lost after every printer reboot. This occurs because of a firmware-level protection that resets the offset to zero upon startup, causing you to lose your calibration.  
To resolve this, we must store the offset value as a persistent variable that is automatically reloaded at the start of every print.  

Edit _printer.cfg_ and add the following line to the initial _includes_ section:

     ````
     [include macro___set_z_offset.cfg]
     ````

- In the same _printer.cfg_ file, scroll to the end. Just before the auto-generated section (marked by #*#), add the following block if it does not already exist:

     ````
     [save_variables]
     # Fichero en el que guardaremos nuestras variables personalizadas.
     filename: ~/printer_data/config/variables.cfg
     ````
     
- If it doesn’t exist, create an empty file named _variables.cfg_ in your configuration directory.

- Upload or copy the file _macro___set_z_offset.cfg_ into the configuration folder.

- Edit _gcode_macro.cfg_ and locate the _[gcode_macro START_PRINT]_ section.  
  At the very beginning (the first line), insert the following unless it is already there:

     ````
     variable_prepare: 0
     ````

     At the very end of the same section, append::

     ````
     APPLY_USER_Z_OFFSET
     ````

From this point forward, you will see a new macro button named SET_USER_Z with a dropdown arrow. Clicking this allows you to input your desired Z-Offset. The value will be stored in _variables.cfg_ and applied automatically to every print, remaining persistent even after a printer reboot.

  

#### Spanish
Seguramente ya habeis observado que hacemos un ajuste de _Z-Offet_ y al siguiente reinicio de la máquina este se ha perdido. El motivo es una protección del firmware que lo pone a cero en dicho reinicio, perdiéndose el ajuste.
Para evitar ese problema debemos de guardar el vlor como una variable que se cargue en cada impresión.
  
- Edita el fichero _printer.cfg_ y añade en la seccion de los _includes_ inicial la línea:
 
     ````
     [include macro___set_z_offset.cfg]
     ````

- En el mismos archivo _printer.cfg_ iremos al final del mismo. Justo antes de todos los cambios que introduce la K2 iniciandose por #*# debemos de escribir (si no existe):

     ````
     [save_variables]
     # Fichero en el que guardaremos nuestras variables personalizadas.
     filename: ~/printer_data/config/variables.cfg
     ````
- Crearemos, si no existe, un fichero vacío llamado _variables.cfg_ en la carpeta de configuraciones.

- Copia el fichero _macro___set_z_offset.cfg_ a la carpeta de configuración.

- Edita _gcode_macro.cfg_ y  busca la sección _[gcode_macro START_PRINT]_. Al principio de la misma, en la primera linea, activamos las variables insertando la linea, salvo que ya exista  

     ````
     variable_prepare: 0
     ````

     Y en la misma sección, al final de la misma, despues de la última linea, introducimos:

     ````
     APPLY_USER_Z_OFFSET
     ````

A partir de dicho momento disponemos de un nuevo boton de macro llamado _SET_USER_Z_ que tiene una flechita hacia abajo. Esto indica que se nos va a desplegar para introducir el valor de Z-Offset, se almacenara en _variables.cfg_ y se cargará este valors automáticamente en cada impresión aunque se reinicie la impresora.

