¿**Cómo funciona el sistema?**

La carpeta de cada año contiene 4 notebooks:
- 20XX_Downloader.ipynb
- 20XX_Data_Base_Creation.ipynb
- Indicators_20XX.ipynb
- Plots_20XX.ipynb

**Downloader**: En este notebook se encuentra un web scraper que accede a las bases de microdatos del DANE, descarga los archivos .zip, los extrae, elimina todos los contenidos que no sean .csv y organiza los módulos en la carpeta 20XX_Data.

**Data Base Creator**: Aquí se limpian los datos y se preparan para aplicar un merge entre todos los módulos y crear la base de datos principal, que es donde se consultará toda la información para la creación de los indicadores. Esta base de datos principal se llama emicronXX.

**Indicators**: Aquí suceden todos los cálculos de los indicadores, que se almacenan en objetos pandas para ser consultados luego en la interfaz de usuario de Jupyter.

**Plots**: Aquí se construyen todos los gráficos. A cada indicador le corresponde un gráfico, y estos objetos se almacenan como funciones.

Además, encontramos:
- executer.ipynb
- reset.ipynb

**Executer**: Este notebook revisa la disponibilidad de las librerías, y en caso de que falte alguna, la descarga automáticamente. Luego, ejecuta los scripts en las carpetas de cada año, importa todos los objetos creados en esas carpetas y, con un sistema de widgets, crea la interfaz de usuario básica, donde puedes seleccionar el año, categoría e indicador.

**Reset**: Al ejecutar el notebook de reset, se eliminan todos los datos y el proyecto vuelve a su estado original.

---

**NOTA**: Basta con hacer clic en "RUN/RUN ALL CELLS" en el notebook del executer para que todo funcione sin problemas.
