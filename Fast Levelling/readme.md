### English
The K2 features a function known as _Adaptive Leveling_. Instead of probing the entire build plate, the printer performs a leveling test only on the specific area where the model will be printed. To enable this feature, follow these steps:  

- Edit your configuration file and locate the parameter _forced_leveling_ and set its value to _false_.

- Save the changes and perform a Firmware Restart in Klipper.

- On the physical printer screen, manually disable Flow Calibration and Pressure Advance calibrations.

- When you start a print, ensure the Calibration option is enabled in your slicer or on the machine.

The first print after a reboot or power cycle will still perform a full bed mesh (entire plate). However, all subsequent prints will be significantly faster, as the printer will only probe the specific footprint of the model being printed.  


### Spanish
Existe una función den la K2 llamada _nivelación adaptativa_, lo que es un test de nivelación pero no de la cama completa, solamente de la zona que va a ocupar la impresión. Para ello hay que seguir unos sencillos pasos:  

- Editar el fichero de configuración _printer.cfg_

- Buscar el parámetro __forced_leveling__ y poner su valor en false.

- Guardar y reiniciar Klipper

- En la pantalla de la impresora desactivar las calibraciones de flujo y de Pressure Advance

- Imprimir con la opcion de calibraciones activada. Si bien en la primera impresión tras un reinicio o apagado será de cama completa, el resto de impresiones serán mas rápidas al ser solo de la zona de impresión.


