# Ciclo de vida del dato (5b):

 <h2> ¿Cómo se gestionan los datos desde su generación hasta su eliminación en tu proyecto?</h2>

En mi proyecto, los datos se gestionan siguiendo un ciclo claro:

<h3>1 Entrada (Generación del dato) </h3> 
Los datos se generan cuando el usuario carga archivos PDF. El programa extrae el texto de cada página seleccionada utilizando librerías como PyPDF2 y PyMuPDF (fitz).

<h3>2 Procesamiento</h3> 
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

<h5>Para:</h5> 

Guardar historial de traducciones.
   
Almacenar fecha, idioma, nombre del archivo.
   
Permitir reabrir trabajos anteriores.

<h3>Sistema de logs</h3> 

<h5>Guardar en un archivo .log:</h5> 

Errores de traducción.

Archivos procesados.

Tiempo de ejecución.

<h3>Caché de traducciones</h3>

<h5>Guardar frases ya traducidas para:</h5> 

Evitar repetir llamadas al traductor.

Aumentar velocidad.

Reducir consumo de API.

<h3>Sistema de usuarios</h3>

<h5>Permitir perfiles con:</h5> 

Configuraciones guardadas.

Idioma preferido.

Carpeta de salida predeterminada.

# Almacenamiento en la nube (5f):

<h2>Si tu software utiliza almacenamiento en la nube, ¿cómo garantizas la seguridad y disponibilidad de los datos?</h2>

Actualmente mi software no almacena archivos en la nube, ya que todo el procesamiento se realiza de forma local en el equipo del usuario.

Sin embargo, si utilizara almacenamiento en la nube, garantizaría la seguridad y disponibilidad mediante:

Cifrado de datos tanto en tránsito (HTTPS/TLS) como en reposo.

Autenticación segura de usuarios, incluyendo contraseñas cifradas y verificación en dos pasos.

Control de accesos, para que cada usuario solo pueda acceder a sus propios archivos.

Copias de seguridad automáticas en servidores redundantes.

Uso de proveedores con alta disponibilidad (99,9% o superior) para evitar pérdidas de datos.

De esta forma se protegería la confidencialidad, integridad y disponibilidad de la información.

<h2>¿Qué alternativas consideraste para almacenar datos y por qué elegiste tu solución actual?</h2> 

Consideré principalmente dos opciones:

<h3>Almacenamiento local</h3> 

<h5>Ventajas:</h5> 

Mayor privacidad.

No depende de conexión a internet.

Procesamiento más rápido.

No requiere costes de servidor.

Elegí esta opción porque mi aplicación está diseñada como herramienta de escritorio y prioriza la seguridad y el control del usuario sobre sus documentos.

<h3>Almacenamiento en la nube</h3> 

<h5>Ventajas:</h5> 

Acceso desde cualquier dispositivo.

Sincronización automática.

Copias de seguridad externas.

<h5>No la elegí porque:</h5>

Aumenta la complejidad técnica.

Requiere mantenimiento de servidores.

Implica mayor responsabilidad legal en protección de datos.

<h2>Si no usas la nube, ¿cómo podrías integrarla en futuras versiones?</h2>

<h3>En futuras versiones podría integrarse la nube mediante:</h3> 

Sistema de cuentas de usuario con inicio de sesión.

Subida automática de archivos traducidos a servicios como Google Drive o OneDrive.

Base de datos online para guardar historial de traducciones.

API propia que procese documentos desde un servidor remoto.

Esto permitiría sincronización entre dispositivos y almacenamiento seguro externo.
