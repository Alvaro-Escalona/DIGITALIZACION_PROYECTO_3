# Ciclo de vida del dato (5b):

 <h2> ¿Cómo se gestionan los datos desde su generación hasta su eliminación en tu proyecto? </h2>

En mi proyecto, los datos se gestionan siguiendo un ciclo claro:

1. Entrada (Generación del dato)
Los datos se generan cuando el usuario carga archivos PDF. El programa extrae el texto de cada página seleccionada utilizando librerías como PyPDF2 y PyMuPDF (fitz).

2. Procesamiento
El texto extraído se:

Divide en párrafos.

Se organiza en bloques.

Se envía al traductor automático (deep_translator).

Se limpia y estructura correctamente.

Durante este proceso, los datos se almacenan temporalmente en memoria (listas y diccionarios).

3. Salida (Almacenamiento final)
El resultado traducido se guarda en:

Archivo PDF (usando reportlab)

Archivo Word (.docx) (usando python-docx)

El usuario elige la carpeta destino.

4. Eliminación
No se almacenan datos permanentes en bases de datos ni en servidores externos.
Los datos temporales se eliminan automáticamente al cerrar la aplicación, ya que solo viven en memoria RAM.

Esto hace que el ciclo de vida del dato sea:

Entrada → Procesamiento → Exportación → Eliminación automática
