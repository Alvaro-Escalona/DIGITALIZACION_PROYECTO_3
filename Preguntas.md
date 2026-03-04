# Ciclo de vida del dato (5b):

 <h2> ¿Cómo se gestionan los datos desde su generación hasta su eliminación en tu proyecto? </h2>

En mi proyecto, los datos se gestionan siguiendo un ciclo claro:

<h3>1 Entrada (Generación del dato) </h3> 
Los datos se generan cuando el usuario carga archivos PDF. El programa extrae el texto de cada página seleccionada utilizando librerías como PyPDF2 y PyMuPDF (fitz).

<h3>2 Procesamiento 
</h3> 
<h5>El texto extraído se: </h5>

Divide en párrafos.

Se organiza en bloques.

Se envía al traductor automático (deep_translator).

Se limpia y estructura correctamente.

Durante este proceso, los datos se almacenan temporalmente en memoria (listas y diccionarios).

<h3>3 Salida (Almacenamiento final) </h3>
<h5>El resultado traducido se guarda en:</h5> 

Archivo PDF (usando reportlab)

Archivo Word (.docx) (usando python-docx)

El usuario elige la carpeta destino.

<h3>4 Eliminación </h3> 
No se almacenan datos permanentes en bases de datos ni en servidores externos.
Los datos temporales se eliminan automáticamente al cerrar la aplicación, ya que solo viven en memoria RAM.

Esto hace que el ciclo de vida del dato sea:

Entrada → Procesamiento → Exportación → Eliminación automática

<h2>¿Qué estrategia sigues para garantizar la consistencia e integridad de los datos?</h2>

En el proyecto aplico varias estrategias:

<h3>1 Validación de entrada</h3> 

Solo se permiten archivos .pdf.

Se verifica que las rutas existan.

Se controla que haya páginas seleccionadas antes de traducir.

<h3>2 Control de errores</h3> 

Uso de bloques try/except para evitar que el programa se bloquee.

Si falla una traducción, se conserva el texto original.

<h3>3 Organización estructurada</h3>

Uso de diccionarios (cola_archivos) para asociar cada PDF con sus páginas seleccionadas.

Las páginas se ordenan antes de procesarse para evitar desorden.

<h3>4 Separación por bloques</h3>

El texto se divide en bloques pequeños antes de traducirse para:

Evitar errores por límite de caracteres.

Mantener coherencia en la traducción.

<h3>5 Progreso controlado</h3> 

Se lleva un conteo de bloques traducidos para asegurar que todo el contenido se procesa correctamente.

<h2> Si no trabajas con datos, ¿cómo podrías incluir una funcionalidad que los gestione de forma eficiente? </h2>

Aunque mi aplicación ya trabaja con datos temporales, podría ampliarse incluyendo:

<h3>1 Base de datos SQLite</h3>  

Para:

Guardar historial de traducciones.
   
Almacenar fecha, idioma, nombre del archivo.
   
Permitir reabrir trabajos anteriores.

<h3>Sistema de logs</h3> 

Guardar en un archivo .log:

Errores de traducción.

Archivos procesados.

Tiempo de ejecución.

<h3>Caché de traducciones</h3>

Guardar frases ya traducidas para:

Evitar repetir llamadas al traductor.

Aumentar velocidad.

Reducir consumo de API.

<h3>Sistema de usuarios</h3>

Permitir perfiles con:

Configuraciones guardadas.

Idioma preferido.

Carpeta de salida predeterminada.
