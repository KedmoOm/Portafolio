### Videos of the demonstration of the creation of the project: https://www.youtube.com/playlist?list=PLmolEnkTZku7XiWfIV3ZxWhViavZED2U3
***
## Caso de Uso: Automatización de Informes de Ventas

### Objetivo

Automatizar la generación de informes mensuales de ventas que extraigan datos de un archivo de Excel y produzcan un informe en formato PDF. La automatización incluirá:
Filtrado y Análisis: Utilizar actividades como "Filtrar DataTable" para segmentar los datos por producto, permitiendo un análisis específico del rendimiento de ventas.
Cálculo de Indicadores Clave de Rendimiento (KPI): Aprovechar los datos disponibles (Fecha, Nombre del Vendedor, Producto Vendido, Cantidad Vendida, Precio Total) para calcular métricas esenciales, incluyendo:
Ventas Totales Mensuales: Calcular el monto total de ventas para cada mes sumando el "Precio Total" de todas las transacciones registradas dentro de ese mes. Esto proporcionará una visión completa de los ingresos generados mensualmente.
Cantidad Vendida por Producto: Contar la cantidad total vendida para cada producto para identificar el rendimiento y las necesidades de inventario.

### Herramientas Requeridas

- **UiPath Studio**: Para crear el flujo de trabajo de automatización.
- **Microsoft Excel**: Para almacenar y gestionar los datos de ventas.

## Pasos para la Automatización 

### 1. **Recolección de Datos**

- **Estructura del Archivo Excel**: Asegúrate de que el archivo Excel contenga columnas como:
    - Fecha
    - Nombre del Vendedor
    - Producto Vendido
    - Cantidad Vendida
    - Precio Total
    
### 2. **Creación del Flujo de Trabajo en UiPath**

- **Inicio del Proceso**:
    - Utiliza la actividad "Alcance de Aplicación Excel" para abrir el archivo Excel.
- **Lectura de Datos**:
    - Emplea la actividad "Leer Rango" para extraer todos los datos relevantes en una variable DataTable.
- **Filtrado y Análisis**:
    - Usa actividades como "Filtrar DataTable" para segmentar los datos por vendedor o producto según sea necesario.
    - **Calcular Indicadores Clave de Rendimiento (KPI)**:
        - Utiliza los datos disponibles (Fecha, Nombre del Vendedor, Producto Vendido, Cantidad Vendida, Precio Total) para calcular métricas importantes. Por ejemplo:
            - **Ventas Totales Mensuales**: Calcula el monto total de ventas para cada mes sumando el "Precio Total" de todas las transacciones registradas dentro de ese mes. Esto te dará una visión clara de cuánto ingreso se generó cada mes.
            - **Cantidad Vendida por Producto**: Cuenta la cantidad total vendida para cada producto.

### 3. **Generación del Informe**

- **Diseño del Informe**:
    - Utiliza una plantilla predefinida en Word o crea un nuevo documento donde se insertarán los resultados.
    - Usa la actividad "Alcance de Aplicación Word" para abrir y modificar el documento.
- **Inserción de Datos**:
    - Inserta los resultados calculados en el documento, utilizando marcadores o tablas para una presentación clara.

### 4. **Exportación a PDF**

- Una vez que el informe esté completo en Word, utiliza la actividad "Exportar a PDF" para guardar el documento en formato PDF.

### Resultados Esperados

- **Ahorro de Tiempo**: La automatización reduce significativamente el tiempo requerido para compilar y generar informes, permitiendo al equipo centrarse en análisis más estratégicos.
- **Mejora en la Precisión**: Al eliminar la entrada manual, se reducen los errores en los informes.
- **Informes Consistentes**: Los informes generados son consistentes en formato y contenido, facilitando la toma de decisiones basada en datos.

### Puntos a Aclarar y Mejoras
- Solo necesitas colocar un archivo de Excel en la carpeta "Input", el nombre no importa. Lo único importante es que debe haber solo un archivo, ya que múltiples archivos en la carpeta pueden sobrescribir información y causar errores.
- Todo este proyecto trabaja con archivos Excel que tienen la misma estructura. Los únicos pasos que el usuario necesita seguir son: copiar y pegar el Excel en la carpeta "Input" del proyecto, ejecutar el proceso y el informe debería aparecer en la carpeta "Output" del proyecto. (La única especificación requerida es el formato de datos para "Date").
- El formato de fecha podría ser, por ejemplo: Agu día-año, Dic día-año, Oct día-año (Tiene que ser un formato con los meses en ingles).
- El proceso debería funcionar correctamente con otros datos que sigan la misma estructura u orden: (Fecha, Nombre del Vendedor, Producto Vendido, Cantidad Vendida, Precio Total).
- Cuando el proyecto termine, puedes mover el archivo de Excel con la información nueva y antigua a otra carpeta o eliminarlo. Una vez que la carpeta 'input' esté vacía, puedes añadir un nuevo archivo de Excel."
- Algunas actividades fueron renombradas por claridad.
- Todo este proyecto fue creado sin el uso de tutoriales en video o documentación, confiando únicamente en mis propias habilidades y conocimientos adquiridos en UiPath Academy para demostrar habilidades de resolución de problemas.

### Puntos que Aprendí:
- Debo copiar todos los datos predeterminados y hacer modificaciones en otra hoja o archivo para evitar pérdida de datos.
- En la actividad "Leer Rango", se debe incluir solo las columnas o datos específicos necesarios para cálculos o análisis para evitar procesamiento adicional y uso innecesario de memoria.

***
## Use Case: Sales Report Automation

### Objective

Automate the generation of monthly sales reports that extract data from an Excel file and produce a report in PDF format. The automation will include:
Filtering and Analysis: Utilize activities like "Filter DataTable" to segment the data by product, allowing for targeted analysis of sales performance.
Calculation of Key Performance Indicators (KPIs): Leverage the available data (Date, Product Sold, Quantity Sold, Total Price) to compute essential metrics, including:
Monthly Total Sales: Calculate the total sales amount for each month by summing the "Total Price" for all transactions recorded within that month. This will provide a comprehensive overview of revenue generated on a monthly basis.
Quantity Sold per Product: Count the total quantity sold for each product to identify performance and inventory needs.

### Required Tools

- **UiPath Studio**: To create the automation workflow.
- **Microsoft Excel**: To store and manage sales data.



## Steps for Automation 

### 1. **Data Collection**

- **Excel File Structure**: Ensure that the Excel file contains columns such as:
    - Date
    - Salesperson Name
    - Product Sold
    - Quantity Sold
    - Total Price
    
### 2. **Creating the Workflow in UiPath**

- **Process Start**:
    - Used the "Excel Application Scope" activity to open the Excel file.
- **Reading Data**:
    - Employ the "Read Range" activity to extract all relevant data into a DataTable variable.
- **Filtering and Analysis**:
    - Used activities like "Filter DataTable" to segment data by salesperson or product as needed.
    - **Calculate Key Performance Indicators (KPIs)**:
        - Use the available data (Date, Salesperson Name, Product Sold, Quantity Sold, Total Price) to calculate important metrics. For example:
            - **Monthly Total Sales**: Calculate the total sales amount for each month by summing the "Total Price" for all transactions recorded within that month. This gives you a clear view of how much revenue was generated each month.
            - **Quantity Sold per Product**: Count the total quantity sold for each product.

### 3. **Generating the Report**

- **Report Design**:
    - Used a predefined template in Word or create a new document where results will be inserted.
    - Used the "Word Application Scope" activity to open and modify the document.
- **Inserting Data**:
    - Insert calculated results into the document, using bookmarks or tables for clear presentation.

### 4. **Exporting to PDF**

- Once the report is completed in Word, use the "Export to PDF" activity to save the document in PDF format.

### Expected Results

- **Time Savings**: Automation significantly reduces the time required to compile and generate reports, allowing the team to focus on more strategic analysis.
- **Improved Accuracy**: By eliminating manual entry, errors in reports are reduced.
- **Consistent Reports**: Generated reports are consistent in format and content, facilitating data-driven decision-making. 

### Points to Clarify and Improvements
- You only need to place one Excel file in the input folder; the name doesn't matter. The only important thing is that there should be only one file, as multiple files in the folder can overwrite information and cause errors.
- This entire project works with Excel files that have the same structure. The only steps the user needs to follow are: copy and paste the Excel file into the project's "Input" folder, run the process, and the report should appear in the project's "Output" folder. (The only required specification is the data format for "Date").
- The date format could be, for example: Aug day-year, Dec day-year, Oct day-year.
- The process should work correctly with other data that follows the same structure or order: (Date, Seller's Name, Product Sold, Quantity Sold, Total Price).
- When the project ends, you can move the Excel file with the new and old information to another folder or delete it. Once the 'input' folder is empty, you can add a new Excel file.
- Some activities were renamed for clarity.
- This entire project was created without the use of video tutorials or documentation, relying solely on my own skills and knowledge acquired from UiPath Academy to demonstrate problem-solving abilities.

### Points I learned:
- I should copy all of the default data and make modifications in another sheet or file to avoid data loss.
- In the "Read Range" activity, we should include only the columns or specific data needed for calculations or analysis to avoid extra proccesing and memory usage
