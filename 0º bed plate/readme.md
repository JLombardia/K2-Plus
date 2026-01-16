When using a "frosted" cold plate for PLA printing, the K2 firmware prevents us from turning off the heated bed or using values below 30°C. This is a firmware-level restriction. This can be bypassed using an override macro that executes at the start of every print. By setting a value in the slicer below 25°C (e.g., 10°C), the macro will detect the low setpoint and prevent the bed from heating.

Two macros, M140 and M190, are created to rename and replace the standard commands with M140.1 and M190.1. These macros effectively suppress the heating command, allowing for "cold printing."

- Edit the printer.cfg file and add the following line to the initial _includes_:

     ````
     [include macro__placa_fria_cero_grados.cfg]
     ````

The process is fully automated. Simply set the Bed Temperature in your slicer to any value below 25°C. When the print begins, the firmware will intercept the command and the bed will remain powered off.


### Spanish  

Cuando utilizamos una placa fría tipo frosted para imprimir con PLA nos encontramos que la K2 no nos deja apagar la cama ni utilizar valores por debajo de los 30º. Es un bloqueo por parte del firmware. Esto se puede solventar mediante un macro de sustitución que se ejecute cada vez que se imprime. Si configuramos en el slicer un valor menor, por ejemplo 10º, se detectará un valor menor de 25º y no se encenderá la cama.  
Se crean dos macros M140 y M190 renombrando los existentes y que se utilizan habitualmente por M140.1 y M190.1. Estos macros no encienden la cama y se imprime en frio. 

- Edita el fichero _printer.cfg_ y añade en la seccion de includes inicial la línea:
 
     ````
     [include macro__placa_fria_cero_grados.cfg]
     ````

- Copia el fichero _macro__placa_fria_cero_grados.cfg_ a la carpeta de configuración.

El proceso es automático, solo pon un valor menor de 25º en la temperatura de la cama en el slicer y cuando se imprima la cama no se encederá.
