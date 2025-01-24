Video de creación del proyecto: https://www.youtube.com/watch?v=xzGWwgY45T0
---

# **Automatización de la Actualización del Inventario**

### **Descripción General**

Este caso de uso aborda la **automatización del proceso de actualización del inventario** en una base de datos, a partir varios archivos CSV que contiene registros de entradas y salidas de productos. La solución incluye la lectura del archivo CSV, la conexión a la base de datos para garantizar que el inventario se mantenga actualizado. Además, al finalizar el proceso, se envía un correo electrónico al administrador o encargado para notificar la carga exitosa de la nueva información. La implementación de esta solución no solo optimiza la eficiencia operativa, sino que también asegura la precisión de los datos del inventario.

---

### **Herramientas Utilizadas**

- **Microsoft Access**: Para la gestión de la base de datos.
- **UiPath Studio X**: Para la automatización del proceso.
- [**generatedata**](http://generaterandomdata.com/): Para la generación de datos ficticios utilizados en pruebas.
- **Trello**: Para la organización de tareas y prioridades del proyecto.
- **Microsoft Excel**: Para la manipulación y modificación de datos.

---

### **Implementación**

1. **Modificación del archivo CSV**:
    - Se utilizó una serie de actividades para eliminar el símbolo de moneda del archivo.
2. **Lectura del archivo CSV**:
    - Se empleó una actividad que permite leer el contenido del archivo y generar un DataTable como resultado.
3. **Validación del archivo**:
    - Se creó un condicional para verificar si el número de columnas es igual a 8, determinando si el archivo corresponde a registros de entradas o salidas.
4. **Conexión a la base de datos**:
    - Se estableció una conexión con Microsoft Access para gestionar los datos.
5. **Actualización del inventario**:
    - Se implementó una actividad “Insert” para guardar los registros del DataTable en la base de datos.
6. **Confirmación y notificación**:
    - Se utilizó una actividad para enviar un correo electrónico al administrador o encargado, confirmando la ejecución exitosa del proceso.

---

### **Beneficios Esperados**

- **Mayor velocidad y precisión**: La automatización reduce significativamente los errores humanos y acelera la actualización del inventario, permitiendo al personal centrarse en tareas estratégicas.
- **Eficiencia operativa**: La eliminación de procesos manuales minimiza costos operativos y optimiza recursos.

---

### **Puntos Aprendidos**

- La implementación del sistema fue un ejercicio práctico valioso para aplicar conocimientos de UiPath y Excel.
- El uso de metodologías ágiles, como SCRUM, facilitó la gestión eficiente del proyecto, permitiendo adaptaciones rápidas ante cambios en los requisitos.
- Se identificó que los espacios en los encabezados de las columnas ocasionan errores al cargar información en la base de datos; por ello, se eliminaron para evitar problemas.
- El símbolo “$” presentó incompatibilidades al intentar convertir valores monetarios a decimales, lo que llevó a eliminarlo durante la preparación de los datos.
- Se adquirió experiencia en la conexión y transferencia de información a bases de datos desde UiPath Studio.

---

### **Puntos a Aclarar**

- Se debe asignar un correo para enviar en la actividad "Enviar correo al administrador", ya que por defecto se dejo sin correo.
- La automatización puede fallar debido a que utiliza rutas de carpeta muy especificas, por lo cual se recomienda modificar la ruta donde se toma el archivo ".laccdb" por la ruta donde el usuario guardo el archivo.
- No se siguieron tutoriales o guías externas durante la creación del proyecto, lo que destaca la capacidad de resolución de problemas y creatividad.
- La automatización fue mejorada al implementar un bucle “For Each”, permitiendo cargar múltiples archivos CSV con solo copiarlos en la carpeta “Entrada”. Estos archivos deben tener la misma estructura de columnas, incluyendo nombres sin espacios.
- El sistema puede ser mejorado para programar ejecuciones automáticas en horarios y días específicos, según las preferencias del usuario.
- Link del proyecto en Trello con enfoque SCRUM: [Trello Board](https://trello.com/b/wNKW3G0F).

**Estructura de las Tablas Utilizadas**

**Registros de Entradas**

1. **Fecha de Entrada**: Fecha de recepción del producto.
2. **Nombre del Producto**: Identificación clara del producto recibido.
3. **Descripción del Producto**: Detalles adicionales (tamaño, color, etc.).
4. **Cantidad Recibida**: Número de unidades recibidas.
5. **Precio Unitario**: Costo por unidad del producto.
6. **Proveedor**: Nombre del proveedor.
7. **Número de Orden de Compra**: Referencia a la orden de compra asociada.
8. **Ubicación en Almacén**: Lugar específico de almacenamiento.

**Registros de Salidas**

1. **Fecha de Salida**: Fecha de despacho o venta del producto.
2. **Nombre del Producto**: Identificación clara del producto.
3. **Descripción del Producto**: Detalles adicionales (tamaño, color, etc.).
4. **Cantidad Vendida/Despachada**: Número de unidades que salen del inventario.
5. **Precio Unitario**: Costo por unidad al cliente.
6. **Cliente o Destinatario**: Persona o entidad a la que se despacha el producto.
7. **Motivo de la Salida**: Razón de la salida (venta, devolución, etc.).
8. **Número de Factura o Ticket**: Referencia de la transacción.
9. **Método de Envío o Entrega**: Detalles de la entrega al cliente (si aplica).
