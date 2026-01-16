#### English
The Skew Correction feature calibrates the proportionality between the X and Y axes. The required values can be obtained by measuring dimensional accuracy on the X and Y axes using calibration prints such as the Califlor (also known as Fleur de Cali or CaliStar, which is highly recommended).  
This project is available at GitHub in https://github.com/dirtdigger/fleur_de_cali, and there is a compiled version with a local web interface on Printables at https://www.printables.com/model/778188-calistar-parametric-open-source-alternative-to-cal. Here you can download a compressed file containing the models and an index.html file. Opening this file allows you to input your measurements to calculate both filament shrinkage/expansion (for maximum dimensional precision) and the skew value.  
  
To avoid restarting the printer every time these parameters are modified, we use variables that are loaded at the start of each print. This ensures changes are applied immediately without a reboot.

- Edit _printer.cfg_ and add the following line to the initial _includes_ section:

     ````
     [include macro___set_skew_correction.cfg]
     ````

- In the same printer.cfg file, go to the very end (just before the #*# auto-generated section) and insert:

     ````
     [save_variables]
     # File where custom variables will be stored.
     filename: ~/printer_data/config/variables.cfg
     
     [skew_correction]
     # Block enabled for skew adjustment.     ````
     ````

- If it does not already exist, create an empty file named _variables.cfg_ in the configuration folder.  

- Copy the file _macro___set_skew_correction.cfg_ into the configuration folder.

- Edit _gcode_macro.cfg_ and locate the _[gcode_macro START_PRINT]_ section. At the very beginning of thes ection, add:  

     ````
     variable_prepare: 0
     ````

  At the very end of the same section, append the following line:

     ````
     SET_MY_SKEW
     ````

Once configured, a new macro button named _SET_USER_SKEW_ will appear with a dropdown arrow. Clicking this will allow you to input your calculated values. These will be stored in _variables.cfg_ and automatically applied at the start of every print.  

  

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

