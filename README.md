# Proyecto_Digitalizacion
Transversor PDF es una herramienta de productividad diseñada para la gestión de documentos multilingües. Permite la traducción automatizada de archivos PDF manteniendo una estructura lógica de párrafos y exportando a formatos editables (.docx) o lectura (.pdf).

Características principales:
Interfaz gráfica moderna (Dark Mode) con customtkinter.

Sistema Drag & Drop para carga masiva de archivos.

Selector visual de páginas para traducción parcial.

Motor de traducción basado en deep-translator (Google Translate API).

Procesamiento en segundo plano (threading) para evitar bloqueos de la interfaz.

# ¿Qué hace el código?

Gestión de Archivos: Permite cargar PDFs mediante botones o arrastrándolos directamente a la interfaz (Drag & Drop).

Edición Visual: Al hacer doble clic en un archivo, abre un selector de páginas donde puedes elegir específicamente qué partes del documento quieres procesar.

Traducción y Conversión: Extrae el texto manteniendo la estructura de párrafos, lo traduce mediante el motor de Google y lo exporta a un nuevo archivo PDF o Word (.docx).

Interfaz Fluida: Utiliza hilos (threading) para que la aplicación no se bloquee mientras traduce, mostrando una barra de progreso en tiempo real.

# Manual de usuario
1. Carga de archivos: Arrastra los PDFs directamente a la ventana o usa los botones "Añadir PDFs/Carpeta".

2. Selección de páginas: Haz doble clic sobre cualquier documento en la lista para abrir el editor visual y marcar solo las páginas que te interesan.

3. Configuración: Elige la carpeta de destino, el idioma de salida y el formato (PDF o Word).

4. Estructura: Selecciona "Bloque continuo" para un texto fluido o "Separado página por página" para mantener la división original.

5. Ejecución: Pulsa "Traducir todo" y sigue el progreso en la ventana emergente.

# Cómo probarlo (Instrucciones de uso)
Para ejecutar el código en tu ordenador, sigue estos pasos:

Paso 1: Instalar las dependencias
Necesitas tener Python instalado. Abre una terminal en la carpeta de tu proyecto y ejecuta el siguiente comando para instalar las librerías necesarias:

pip install customtkinter tkinterdnd2 Pillow PyPDF2 deep-translator reportlab python-docx pymupdf

Paso 2: Ejecutar la aplicación en el entorno que prefiera o lanza el script con el comando:

python traductorv4.py

# Realizar una prueba completa
Carga: Busca un archivo PDF en tu equipo y arrástralo dentro de la ventana del programa.

Selección: Haz doble clic sobre el icono del PDF que aparece en la lista. Marca solo un par de páginas para que la prueba sea rápida y dale a "Guardar selección".

Destino: Pulsa en "Elegir carpeta de salida" y selecciona, por ejemplo, tu Escritorio.

Traducción: Elige el idioma (ej. de Inglés a Español), selecciona "Exportar a Word" y pulsa el botón verde "Traducir todo".

Verificación: Espera a que la barra de progreso llegue al 100% y revisa tu Escritorio para ver el archivo generado.
