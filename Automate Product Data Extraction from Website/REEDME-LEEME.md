Video de creación del proyecto: https://youtu.be/P8Q_bpAbCwg
***

## Use Case: Automatización de la Extracción de Datos de Productos desde un Sitio Web de Comercio Electrónico

### Objective

El objetivo de este proyecto de automatización es extraer datos de productos, incluyendo **nombres**, **precios** y **calificaciones**, de un sitio web de comercio electrónico accesible públicamente (por ejemplo, Amazon). Esta automatización demostrará la efectividad de los procesos de extracción de datos sin intervención manual.

### Herramientas Requeridas

- **UiPath Studio**: Para crear el flujo de trabajo de automatización.
- **Microsoft Excel**: Para almacenar y gestionar los datos de productos extraídos.
- **Sitio Web de Comercio Electrónico**: En este ejemplo, utilizaré Amazon.com.

### Pasos para la Automatización

1. **Identificar el Sitio Web Objetivo**

   - Determino las páginas específicas en Amazon que contienen los datos del producto que deseo extraer. Esto puede incluir páginas de resultados de búsqueda o páginas individuales de detalles del producto.

2. **Lanzar el Navegador Web**

   - Utilizo la actividad **Launch Browser** para abrir la página web objetivo en Amazon, asegurándome de que el navegador esté configurado para navegar a la URL correcta.

3. **Extraer Datos del Producto**

   - Utilizo el **Data Scraping Wizard** en UiPath para seleccionar los elementos que quiero extraer:
     - **Nombre del Producto**: Identifico y selecciono el elemento HTML que contiene el nombre del producto.
     - **Precio**: Selecciono el elemento HTML que muestra el precio del producto.
     - **Calificación**: Si está disponible, selecciono el elemento que muestra las calificaciones de los clientes.
   - El asistente generará una variable DataTable que contendrá todos los datos extraídos, los cuales se pueden manipular más adelante según sea necesario.

4. **Almacenar Datos Extraídos**

   - Después de extraer, almaceno los datos extraídos en un formato estructurado (por ejemplo, CSV o Excel) para su análisis o informes posteriores. Utilizo actividades como **Write Range** para guardar la DataTable en un archivo Excel.
   1. **Filtrar datos**
      - Después de almacenar los datos en un archivo Excel, filtro los datos; por ejemplo, elimino los productos que no tienen precio.

### Resultados Esperados

- **Eficiencia Temporal**: La automatización reduce significativamente el tiempo requerido para la recolección de datos en comparación con métodos manuales.
- **Precisión de Datos**: Al eliminar errores humanos en la entrada de datos, se mejora la precisión de los datos recolectados.
- **Escalabilidad**: La automatización se puede ajustar para extraer productos o categorías adicionales sin una reconfiguración extensa.

### Puntos a Aclarar

- El proyecto debe funcionar y dejar un archivo Excel en la carpeta "Output".
- Este proyecto debe funcionar con otros productos de Amazon.com (solo necesita cambiar la URL o ruta).
- Este proyecto puede fallar en otros sitios web debido a sus estructuras diferentes.

***
## Use Case: Automating Product Data Extraction from an E-Commerce Website

### Objective

The objective of this automation project is to extract product data, including **names**, **prices**, and **ratings**, from a publicly accessible e-commerce website (e.g., Amazon). This automation will demonstrate the effectiveness of data extraction processes without manual intervention.

### Required Tools

- **UiPath Studio**: To create the automation workflow.
- **Microsoft Excel**: To store and manage the scraped product data.
- **E-commerce Website**: In this example, I will use Amazon.com.

### Steps for Automation

1. **Identify the Target Website**

   - I determine the specific pages on Amazon that contain the product data I wish to scrape. This can include search results pages or individual product detail pages.

2. **Launch the Web Browser**

   - I use the **Launch Browser** activity to open the target webpage on Amazon, ensuring that the browser is set to navigate to the correct URL.

3. **Scrape Product Data**

   - I utilize the **Data Scraping Wizard** in UiPath to select the elements I want to extract:
     - **Product Name**: I identify and select the HTML element that contains the product name.
     - **Price**: I select the HTML element that displays the product price.
     - **Rating**: If available, I select the element that shows customer ratings.
   - The wizard will generate a DataTable variable containing all scraped data, which I can manipulate further as needed.

4. **Store Scraped Data**

   - After scraping, I store the extracted data in a structured format (e.g., CSV or Excel) for further analysis or reporting. I use activities like **Write Range** to save the DataTable into an Excel file.
   1. **Filtering data**
      - After storing the data in an Excel file, I filter the data; for example, I eliminate products that don’t have a price.

### Expected Results

- **Time Efficiency**: Automation significantly reduces the time required for data collection compared to manual scraping methods.
- **Data Accuracy**: By eliminating human error in data entry, the accuracy of collected data is improved.
- **Scalability**: The automation can be adjusted to scrape additional products or categories without extensive reconfiguration.

### Points to Clarify

- The project should work and leave an Excel file in the "Output" folder.
- This project should work with other products from Amazon.com (it only needs to change the URL or path).
- This project may fail on other websites due to their different structures.
