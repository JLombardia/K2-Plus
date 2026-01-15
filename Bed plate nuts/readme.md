#### English
An important adjustment is leveling the bed horizontally with respect to the X and Y axes. To do this, it is necessary to adjust the nuts located beneath the heated bed and perform a diagonal leveling process.
In the first step, the printer will heat the bed and the nozzle, home itself, and take a reference point. For the remaining steps, you will need either a 0.10mm metal feeler gauge (highly recommended) or a standard sheet of paper, which typically measures around 0.08mm. You will go corner by corner, adjusting the bottom nut to set the level. It is advisable to repeat this process a couple of times.  

- Edit the file _printer.cfg_ and add in the includes section the line:
 
     ````
     [include macro___led_extrusor.cfg]
     ````

- Copy the file _macro___level_nuts.cfg_ to the configuration folder.


To start the process, press the NUT_1_CENTER button and wait for the printer to heat up and home to the center of the bed. Use the subsequent buttons (NUT_2..., NUT_3..., etc.) to perform the adjustments. Repeat steps 2 through 5 again. Finally, NUT_6_END will lift the nozzle and cool down the assembly.


#### Spanish
Un ajuste importante es nivelar la cama horizontalmente respecto a los ejes X e Y. Para ello es necesario retocar las tuercas existentes por debajo de la cama caliente y realizar un proceso de ajuste en diagonal.
En el primer paso la impresora calentará cama y nozzle, se centrará y tomará referencia. Para el resto necesitaremos bien una galga metálicade 0.10mm que es lo más recomendable, o bien la típica hoja de papel, que viene a medir 0.08mm. Iremos haciendo esquina por esquina tocando la tuerca inferior para ajustar el nivel. Es conveniente repetir el proceso un par de veces.

- Edita el fichero _printer.cfg_ y añade en la seccion de includes inicial la línea:
 
     ````
     [include macro___level_nuts.cfg]
     ````

- Copia el fichero _macro___level_nuts.cfg_ a la carpeta de configuración.


Para realizar el proceso pulsa el botón _NUT_1_CENTER_ y esperar a que caliente y se centre en la cama. Con los sucesivos _NUT_2_..._, _NUT_3_..., ... hacemos el ajuste. Repetir 2 a 5 de nuevo. Finalmente _NUT_6_END_ levanta el nozzle y enfría el conjunto.

