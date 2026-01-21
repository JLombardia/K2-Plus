## English
This macro try to simplify manual bed tramming, ensuring the bed is perfectly parallel to the X and Y axes.  
Instead of displaying raw millimeter values that are hard to interpret, this macro calculates exactly how much you need to turn each knob using a _clock face metaphor_.
  
  
### 🌟 Key Features
* **Fixed Reference:** Uses the Front Left (FL) corner as the "zero point" (Horizon Reference).
* **"Clock" System:** Divides each knob into 12 positions (like the hours on a clock). The macro tells you exactly how many "hours" or positions to turn.
* **Clear Instructions:** Displays simple console commands: `SCREW` (Tighten) or `UNSCREW` (Loosen).
* **Range Protection:** If the deviation is too large (>2mm), the macro warns you to adjust the base reference instead of over-compressing springs.
  
  
### ⚙️ Installation

1.  Edit the file _printer.cfg_ and add in the includes section the line:
 
     ````
     [include macro___horizon_levelling.cfg]
     ````

2.	Copy the file _macro___horizon_levelling.cfg_ to the configuration folder.
3.  Adjust the `variable_screw_pitch` if your screws are not standard (M4 = 0.7mm).
4.  **Important:** Verify the coordinates in `_HORIZON_VARS`. Ensure the probe (not the nozzle) is positioned directly above the screws.
  
  
### 🚀 Usage
1.  Home your printer (`G28`).
2.  Run the macro for the first corner, for example: `HORIZON_1_RR` (Rear Right).
3.  The printer will measure the reference (FL) and then the target corner.
4.  Read the console. It will display a message like:
    > *ACTION: SCREW (Tighten/Right) -> 3 positions (hours).*
5.  Make the manual adjustment and repeat the measurement until it says "PERFECT".
6.  Repeat for `HORIZON_2_RL` and `HORIZON_3_FR`.

There is a STL file with a nut handle. After print, insert and glue them in the original nut. It has 12 lines than you can paint in contrast to do the adjustment easier.  

	
[![model preview](/_assets/bed_nut_handle.png)](/_assets/bed_nut_handle.stl)


## Spanish
El objetivo de esta macro es facilitar el nivelado manual (tramming) de la cama caliente para dejarla perfectamente paralela a los ejes X e Y.  
En lugar de mostrar valores crudos en milímetros difíciles de interpretar, este macro calcula exactamente cuánto debes girar cada tuerca utilizando la _metáfora del reloj_.  


### 🌟 Características Principales
* **Referencia Fija:** Utiliza la esquina Frontal Izquierda (FL) como "punto cero" (Horizon Reference).
* **Sistema de "Horas":** Divide cada tuerca en 12 posiciones (como las horas de un reloj). El macro te dice exactamente cuántas "horas" o posiciones girar.
* **Instrucciones Claras:** Muestra en la consola comandos simples: `SCREW` (Atornillar/Apretar) o `UNSCREW` (Desatornillar/Aflojar).
* **Protección de Rango:** Si la desviación es demasiado grande (>2mm), el macro te avisa para ajustar la referencia base en lugar de forzar los muelles.
  
  
### ⚙️ Instalación
1.  Inserta en _printer.cfg_ la linea:

     ````
     [include macro___horizon_leveling.cfg]
     ````
	 
2.	Carga el fichero _macro___horizon_leveling.cfg_ en tu carpeta de configuración. 
3.  Ajusta la variable `variable_screw_pitch` si tus tornillos no son estándar (M4 = 0.7mm).
4.  **Importante:** Verifica las coordenadas en `_HORIZON_VARS`. Asegúrate de que la sonda (no la boquilla) se posicione justo encima de los tornillos.
  
  
### 🚀 Uso
1.  Haz "Home" en tu impresora (`G28`).
2.  Ejecuta el macro para la primera esquina, por ejemplo: `HORIZON_1_RR` (Trasera Derecha).
3.  La impresora medirá la referencia (FL) y luego la esquina objetivo.
4.  Lee la consola. Te dirá algo como:
    > *ACTION: SCREW (Tighten/Right) -> 3 positions (hours).*
5.  Realiza el ajuste manual y repite la medición hasta que diga "PERFECT".
6.  Repite para `HORIZON_2_RL` y `HORIZON_3_FR`.


Hay un fichero STL con un adaptador a la tuerca original. Tras imprimir se puede insertar esta y pegarla. El adaptador tiene 12 lineas que pueden ser pintadas en contraste para un ajuste mas sencillo.  

  
[![Vista previa del modelo](./_assets/bed_nut_handle.png)](./_assets/bed_nut_handle.stl)

