## English
This macro try to simplify manual bed tramming, ensuring the bed is perfectly parallel to the X and Y axes.  
Instead of displaying raw millimeter values that are hard to interpret, this macro calculates exactly how much you need to turn each knob.
  
1.  Edit the file _printer.cfg_ and add in the includes section the line:
 
     ````
     [include macro___horizon_levelling.cfg]
     ````

	And at the end of _printer.cfg_ add the following section to activate M118 command to send message to the console:
 
     ````
     [respond]  
	 default_type: echo
     ````  
	 
	  

2.	Copy the file _macro___horizon_levelling.cfg_ to the configuration folder.
  
  
3.  Run the macro `HORIZON_START'  
  
4.  Follow instructiones in the console window.

There is a STL file with a nut handle. After print, insert and glue them in the original nut. It has 12 lines than you can paint in contrast to do the adjustment easier. Clcik in the image for 3D viewer and download it.  

	
<div align="center">
  <a href="/_assets/bed_nut_handle.stl">
    <img src="/_assets/bed_nut_handle.png" alt="View and download">
  </a>
  <p><em>Click on the image to see in the 3D viewer and download it</em></p>
</div>
  
  
  
  
  
## Spanish
El objetivo de esta macro es facilitar el nivelado manual (tramming) de la cama caliente para dejarla perfectamente paralela a los ejes X e Y.  
En lugar de mostrar valores en milímetros difíciles de interpretar, este macro calcula exactamente cuánto debes girar cada tuerca.  


1.  Inserta en _printer.cfg_ la linea:

     ````
     [include macro___horizon_leveling.cfg]
 
    ````

	Y al final de _printer.cfg_ hay que añadir la siguiente sección para activar que el comando M118 pueda enviar mensajes a la consola:
 
     ````
     [respond]  
	 default_type: echo
     ``

	 
2.	Carga el fichero _macro___horizon_leveling.cfg_ en tu carpeta de configuración. 
  
3.  Ejecuta el macro `HORIZON_START`  
  
4.  Sigue las instrucciones que se muestran en la ventana de la consola.  



Hay un fichero STL con un adaptador a la tuerca original. Tras imprimir se puede insertar esta y pegarla. El adaptador tiene 12 lineas que pueden ser pintadas en contraste para un ajuste mas sencillo. Click en la imagen para abrir el visor 3D y descargar el fichero STL.  

  
<div align="center">
  <a href="/_assets/bed_nut_handle.stl">
    <img src="/_assets/bed_nut_handle.png" alt="Ver y descargar">
  </a>
  <p><em>Haz clic en la imagen para interactuar con el modelo 3D y descargarlo</em></p>
</div>
