Video de creación del proyecto: https://youtu.be/XO7dceUiBAs

## Caso de Uso: Automatización de Satisfacción del Cliente 🚀

**Descripción General**

Este caso de uso aborda la **automatización de la satisfacción del cliente**, desde la recopilación y análisis de datos hasta la visualización gráfica en Excel. La automatización garantiza rapidez, precisión y un flujo de trabajo eficiente para identificar áreas de mejora y optimizar la experiencia del cliente. Se espera que el RPA sea capaz de realizar consultas a la base de datos y recopilar información clave para su representación en un archivo Excel.

**Objetivos**

- **Recopilación de Datos**: Simular una base de datos con respuestas de clientes sobre satisfacción.
- **Análisis Automatizado**: Generar consultas SQL para identificar patrones clave.
- **Visualización Automática**: Crear gráficos en Excel para presentar los resultados de forma clara y accesible.

**Herramientas Utilizadas**

- **Power Automate**: Para la automatización de tareas.
- **Microsoft Excel**: Para almacenar y graficar resultados.
- **SQLite Database Browser**: Para el análisis y consulta de datos.
- **Trello**: Para la planificación y seguimiento de tareas.
- **Generadata.com**: Página web que permite generar datos aleatorios para alimentar la base de datos.
- **Microsoft Access**: Para la creación de la base de datos.

### Implementación

- **Duración Estimada**: 5 días (1 sprint).
- **Planificación Ágil**: Creación de un *backlog* en [Trello](https://trello.com/b/6sBRWd6B).

**1. Recopilación de Respuestas**

Se diseñará un formulario para recopilar respuestas de clientes con preguntas sobre:

- Información del cliente (Nombre, Correo).
- Satisfacción general (escala 1-5).
- Comentarios abiertos.

**2. Simulación de Base de Datos**

Se implementará una base de datos en **Microsoft Access** para almacenar las respuestas. Ejemplo de la sintaxis:

```sql
CREATE TABLE SatisfaccionCliente (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    Nombre VARCHAR(24),
    Correo VARCHAR(30),
    Producto_Servicio VARCHAR(24),
    Puntuacion INT,
    Comentario TEXT,
    Recomienda_Producto INT
);
```

**3. Alimentación de la Base de Datos con Información Ficticia**

- Se crearon 70 registros ficticios.
- Los registros se guardaron en la base de datos `Bd_SatisfaccionClientes.accdb`.

**4. Análisis Automatizado de Datos**

- Se creó la conexión con la base de datos desde Power Automate.
- Se realizaron consultas SQL automatizadas desde Power Automate, como:

    - **Total de Respuestas y Promedio de Satisfacción**:
    
        ```sql
        SELECT COUNT(*) AS TotalRespuestas, ROUND(AVG(Puntuacion)) AS PromedioSatisfaccion
        FROM SatisfaccionCliente;
        ```

    - **Identificación de Productos con Baja Satisfacción**:
    
        ```sql
        SELECT Producto_Servicio, COUNT(*) AS TotalRespuestas, AVG(Puntuacion) AS Promedio
        FROM SatisfaccionCliente
        GROUP BY Producto_Servicio
        HAVING AVG(Puntuacion) < 3;
        ```

    - **Total de Personas que Recomiendan y No Recomiendan**:
    
        ```sql
        SELECT Recomienda_Producto, COUNT(*) AS TotalRespuestas 
        FROM SatisfaccionCliente 
        GROUP BY Recomienda_Producto;
        ```

    - **Productos con Puntuación Igual o Mayor a 4 y que Recomiendan**:
    
        ```sql
        SELECT Producto_Servicio, Puntuacion, Recomienda_Producto, COUNT(*) AS TotalRespuestas
        FROM SatisfaccionCliente
        WHERE Puntuacion >= 4 AND Recomienda_Producto = 1
        GROUP BY Producto_Servicio, Puntuacion, Recomienda_Producto;
        ```

**5. Automatización de Gráficos en Excel**

- Se dio formato de tabla a los datos consultados en el archivo Excel.

La información analizada fue exportada a un archivo Excel, donde la automatización generó gráficos como:

- **Gráfico de Barras**: Promedio de satisfacción por producto/Servicio, Producto/Servicio de alta calidad, etc .

### Beneficios Esperados

- **Identificación Rápida de Problemas**: Permite a los encargados analizar áreas críticas.
- **Mayor Velocidad y Precisión**: Eliminación de errores humanos y reducción del tiempo.
- **Mejora de la Experiencia del Cliente**: Decisiones informadas basadas en datos.
- **Visualización Clara**: Informes visuales fáciles de entender y comunicar.
- **Escalabilidad**: La automatización sigue funcionando correctamente, incluso si la base de datos crece.

**Puntos Aprendidos**

- Manejo de sub-flujos en Power Automate para una mejor distribución de tareas y visualización de acciones.
- Uso de Access para la creación de bases de datos y su conexión con Power Automate.
- Identificación de errores debido a configuraciones regionales, como el uso de (,) en lugar de (.) para símbolos decimales, que afecta archivos .CSV y aplicaciones de Office.
- Power Automate carece de ciertas funcionalidades presentes en UiPath Studio, como creación de tablas dinámicas o acciones de copiar y pegar, lo que requiere procesos adicionales.
- Uso de expresiones matemáticas en Power Automate.

**Puntos a Aclarar**

- Se utilizó un enfoque basado en la metodología ágil SCRUM.
- El *product backlog* se encuentra en el siguiente enlace: [Trello](https://trello.com/b/6sBRWd6B).
- Power Automate no permite exportar procesos o flujos de trabajo, por lo que la evidencia del proyecto se encuentra en un video en YouTube.
- Este proyecto fue diseñado para demostrar habilidades adquiridas en cursos de Power Automate y SQL.
- No se siguió ningún video tutorial o contenido guiado, con el objetivo de demostrar habilidades en resolución de problemas.
- El proceso funciona correctamente con bases de datos dinámicas, adaptándose a diferentes cantidades de registros.
- La creación de gráficos en Excel puede presentar errores debido a resoluciones de pantalla. Se utilizó una resolución de 1760x990 para este proyecto.
