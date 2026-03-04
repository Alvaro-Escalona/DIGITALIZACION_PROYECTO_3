# Ciclo de vida del dato (5b):

 <h2> ¿Cómo se gestionan los datos desde su generación hasta su eliminación en tu proyecto?</h2>

En mi proyecto, los datos se gestionan siguiendo un ciclo claro:

<h3>1 Entrada (Generación del dato) </h3> 
Los datos se generan cuando el usuario carga archivos PDF. El programa extrae el texto de cada página seleccionada utilizando librerías como PyPDF2 y PyMuPDF (fitz).

<h3>2 Procesamiento</h3> 
<h5>El texto extraído se: </h5>

- Divide en párrafos.

- Se organiza en bloques.

- Se envía al traductor automático (deep_translator).

- Se limpia y estructura correctamente.

Durante este proceso, los datos se almacenan temporalmente en memoria (listas y diccionarios).

<h3>3 Salida (Almacenamiento final) </h3>
<h5>El resultado traducido se guarda en:</h5> 

- Archivo PDF (usando reportlab)

- Archivo Word (.docx) (usando python-docx)

El usuario elige la carpeta destino.

<h3>4 Eliminación </h3> 
No se almacenan datos permanentes en bases de datos ni en servidores externos.
Los datos temporales se eliminan automáticamente al cerrar la aplicación, ya que solo viven en memoria RAM.

Esto hace que el ciclo de vida del dato sea:

Entrada → Procesamiento → Exportación → Eliminación automática

---

<h2>¿Qué estrategia sigues para garantizar la consistencia e integridad de los datos?</h2>

En el proyecto aplico varias estrategias:

<h3>1 Validación de entrada</h3> 

- Solo se permiten archivos .pdf.

- Se verifica que las rutas existan.

- Se controla que haya páginas seleccionadas antes de traducir.

<h3>2 Control de errores</h3> 

- Uso de bloques try/except para evitar que el programa se bloquee.

- Si falla una traducción, se conserva el texto original.

<h3>3 Organización estructurada</h3>

- Uso de diccionarios (cola_archivos) para asociar cada PDF con sus páginas seleccionadas.

- Las páginas se ordenan antes de procesarse para evitar desorden.

<h3>4 Separación por bloques</h3>

El texto se divide en bloques pequeños antes de traducirse para:

- Evitar errores por límite de caracteres.

- Mantener coherencia en la traducción.

<h3>5 Progreso controlado</h3> 

Se lleva un conteo de bloques traducidos para asegurar que todo el contenido se procesa correctamente.

---

<h2> Si no trabajas con datos, ¿cómo podrías incluir una funcionalidad que los gestione de forma eficiente? </h2>

Aunque mi aplicación ya trabaja con datos temporales, podría ampliarse incluyendo:

<h3>1 Base de datos SQLite</h3>  

<h5>Para:</h5> 

- Guardar historial de traducciones.
   
- Almacenar fecha, idioma, nombre del archivo.
   
- Permitir reabrir trabajos anteriores.

<h3>Sistema de logs</h3> 

<h5>Guardar en un archivo .log:</h5> 

- Errores de traducción.

- Archivos procesados.

- Tiempo de ejecución.

<h3>Caché de traducciones</h3>

<h5>Guardar frases ya traducidas para:</h5> 

- Evitar repetir llamadas al traductor.

- Aumentar velocidad.

- Reducir consumo de API.

<h3>Sistema de usuarios</h3>

<h5>Permitir perfiles con:</h5> 

- Configuraciones guardadas.

- Idioma preferido.

- Carpeta de salida predeterminada.

# Almacenamiento en la nube (5f):

<h2>Si tu software utiliza almacenamiento en la nube, ¿cómo garantizas la seguridad y disponibilidad de los datos?</h2>

Actualmente mi software no almacena archivos en la nube, ya que todo el procesamiento se realiza de forma local en el equipo del usuario.

Sin embargo, si utilizara almacenamiento en la nube, garantizaría la seguridad y disponibilidad mediante:

- Cifrado de datos tanto en tránsito (HTTPS/TLS) como en reposo.

- Autenticación segura de usuarios, incluyendo contraseñas cifradas y verificación en dos pasos.

- Control de accesos, para que cada usuario solo pueda acceder a sus propios archivos.

- Copias de seguridad automáticas en servidores redundantes.

- Uso de proveedores con alta disponibilidad (99,9% o superior) para evitar pérdidas de datos.

De esta forma se protegería la confidencialidad, integridad y disponibilidad de la información.

---

<h2>¿Qué alternativas consideraste para almacenar datos y por qué elegiste tu solución actual?</h2> 

Consideré principalmente dos opciones:

<h3>Almacenamiento local</h3> 

<h5>Ventajas:</h5> 

- Mayor privacidad.

- No depende de conexión a internet.

- Procesamiento más rápido.

- No requiere costes de servidor.

Elegí esta opción porque mi aplicación está diseñada como herramienta de escritorio y prioriza la seguridad y el control del usuario sobre sus documentos.

<h3>Almacenamiento en la nube</h3> 

<h5>Ventajas:</h5> 

- Acceso desde cualquier dispositivo.

- Sincronización automática.

- Copias de seguridad externas.

<h5>No la elegí porque:</h5>

- Aumenta la complejidad técnica.

- Requiere mantenimiento de servidores.

- Implica mayor responsabilidad legal en protección de datos.

---

<h2>Si no usas la nube, ¿cómo podrías integrarla en futuras versiones?</h2>

<h3>En futuras versiones podría integrarse la nube mediante:</h3> 

- Sistema de cuentas de usuario con inicio de sesión.

- Subida automática de archivos traducidos a servicios como Google Drive o OneDrive.

- Base de datos online para guardar historial de traducciones.

- API propia que procese documentos desde un servidor remoto.

Esto permitiría sincronización entre dispositivos y almacenamiento seguro externo.

# Seguridad y regulación (5i):

<h2>¿Qué medidas de seguridad implementaste para proteger los datos o procesos en tu proyecto?</h2>

En mi proyecto he implementado principalmente medidas de seguridad a nivel local y de control de errores, ya que la aplicación funciona como herramienta de escritorio y no almacena datos en servidores externos.

<h5>Las principales medidas son:</h5> 

- Procesamiento local de los archivos: los PDFs se procesan en el equipo del usuario, evitando transferencias innecesarias.

- No almacenamiento permanente de datos: los datos se mantienen en memoria temporal y se eliminan al cerrar la aplicación.

- Validación de archivos de entrada: solo se permiten archivos con extensión .pdf.

- Control de errores (try/except): evita fallos del sistema y pérdida de información durante el proceso de traducción.

- Selección manual de carpeta destino: el usuario decide dónde guardar los archivos traducidos.

Estas medidas reducen el riesgo de pérdida de datos o accesos no autorizados.

---

<h2>¿Qué normativas (e.g., GDPR) podrían afectar el uso de tu software y cómo las has tenido en cuenta?</h2>

La normativa principal que podría afectar al uso del software es el:

<h3>📜 Reglamento General de Protección de Datos (GDPR / RGPD)</h3>

Esta normativa europea regula el tratamiento de datos personales.

En mi caso:

- La aplicación no almacena datos personales en servidores propios.

- No existe base de datos de usuarios.

- No se recopila información identificativa.

Sin embargo, si los PDFs contienen datos personales y se utiliza un servicio de traducción online, podría implicar transferencia de datos a terceros.

Por ello, en futuras versiones sería recomendable:

- Informar al usuario mediante una política de privacidad.

- Permitir consentimiento explícito antes de enviar datos a servicios externos.

- Ofrecer una opción de traducción completamente offline.

---

<h2>Si no implementaste medidas de seguridad, ¿qué riesgos potenciales identificas y cómo los abordarías en el futuro?</h2>

Aunque la aplicación es local, identifico algunos riesgos potenciales:

<h3>Riesgos</h3> 

- Envío de información sensible a servicios externos de traducción.

- Posible pérdida de archivos si ocurre un error durante la exportación.

- Falta de cifrado en los archivos generados.

<h3>Soluciones futuras</h3> 

- Implementar cifrado de archivos PDF generados.

- Integrar un traductor offline para evitar envío de datos.

- Añadir sistema de registro (log) para auditoría de procesos.

- Crear política de privacidad y aviso legal.

- Implementar firma digital o verificación de integridad del archivo exportado.

# Implicación de las THD en negocio y planta (2e):

<h2>¿Qué impacto tendría tu software en un entorno de negocio o en una planta industrial?</h2>

Mi software, Transversor PDF, puede tener un impacto significativo en entornos empresariales e industriales, especialmente en empresas que trabajan con documentación técnica en distintos idiomas.

<h5>En un entorno de negocio o planta industrial podría:</h5>

- Facilitar la traducción rápida de manuales técnicos, normativas, fichas de seguridad o especificaciones de maquinaria.

- Reducir tiempos administrativos al eliminar la necesidad de traducciones externas para documentos internos.

- Mejorar la comunicación con proveedores o clientes internacionales.

- Disminuir costes asociados a servicios de traducción tradicionales.

En una planta industrial donde se utilicen manuales en diferentes idiomas, el software permitiría adaptar rápidamente la documentación para operarios o técnicos locales.

---

<h2>¿Cómo crees que tu solución podría mejorar procesos operativos o la toma de decisiones?</h2>

Mi solución mejora procesos operativos de las siguientes maneras:

<h3>Agilización de procesos</h3>

La traducción automática reduce el tiempo necesario para comprender documentación técnica extranjera, permitiendo actuar con mayor rapidez.

<h3>Mayor accesibilidad a la información</h3>

Los trabajadores pueden acceder a documentos en su idioma, lo que reduce errores de interpretación.

<h3>Apoyo a la toma de decisiones</h3>

Los responsables pueden analizar contratos, informes técnicos o normativas internacionales sin depender de terceros, lo que acelera decisiones estratégicas.

<h3>Reducción de errores humanos</h3> 

Al estructurar correctamente los documentos y mantener su formato organizado, se minimiza la pérdida de información relevante.

---

<h2>Si tu proyecto no aplica directamente a negocio o planta, ¿qué otros entornos podrían beneficiarse?</h2>

Además del ámbito empresarial e industrial, otros entornos que podrían beneficiarse son:

- Centros educativos, para traducir artículos científicos o material académico.

- Despachos jurídicos, para revisar contratos internacionales.

- Administraciones públicas, para adaptar documentación oficial.

- Profesionales autónomos, que trabajen con clientes extranjeros.

- Empresas tecnológicas, que necesiten traducir documentación técnica rápidamente.

En general, cualquier organización que gestione documentos en varios idiomas podría beneficiarse de esta herramienta.

# Mejoras en IT y OT (2f):

El software **Transversor PDF** puede facilitar la integración entre entornos IT (Information Technology) y OT (Operational Technology) mediante la estandarización y traducción rápida de documentación técnica.

En entornos industriales, la información generada en planta (OT) como manuales de maquinaria, protocolos de mantenimiento o informes técnicos, muchas veces debe ser analizada o archivada en sistemas IT (ERP, plataformas documentales, sistemas de gestión).

<h5>Mi software permite:</h5> 

- Traducir documentación técnica de fabricantes internacionales.
- Unificar el idioma de los documentos para su almacenamiento digital.
- Facilitar la comunicación entre personal técnico de planta y departamentos administrativos.
- Reducir errores derivados de la mala interpretación de manuales.

De esta forma, actúa como herramienta de apoyo en la digitalización y conexión entre ambos entornos.

---
