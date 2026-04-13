comment post de fb
Script en Python para obtener publicaciones y comentarios de una página de Facebook usando la API Graph y guardarlos en un archivo .txt.

Descripción

Este proyecto permite:

Conectarse a la API de Facebook Graph
Obtener publicaciones de una página
Extraer comentarios asociados a cada post
Guardar la información en un archivo local
Navegar entre múltiples páginas de resultados (paginación)
Requisitos
Python 3.x
Librería requests

Instalación:

pip install requests
Configuración

Antes de ejecutar el script, debes configurar:

access_token: Token de acceso válido de Facebook
{id de página}: ID de la página de Facebook que deseas consultar
api_url = 'https://graph.facebook.com/v17.0/{id de página}/posts'
access_token = '{token de fb}'
Funcionamiento del código
1. Obtener datos de la API
def get_posts_data(url):
Realiza una solicitud GET a la API
Retorna los datos en formato JSON
Maneja errores de conexión
2. Guardar datos en archivo
def save_data_to_file(data, filename):
Recorre los posts obtenidos
Guarda cada post como texto en un archivo .txt
Usa codificación UTF-8
3. Paginación automática

El script recorre múltiples páginas de resultados:

for i in range(10):
Obtiene hasta 10 páginas de resultados (puedes modificar este valor)
Usa el campo paging.next para continuar
Salida

Los datos se guardan en:

D:\WSD\posts_data_2023.txt

Formato:

{'id': '...', 'comments': {...}}
Consideraciones
El token de acceso debe tener permisos adecuados (ej: pages_read_engagement)
La API de Facebook tiene límites de uso (rate limits)
No se recomienda subir el access_token al repositorio (usa variables de entorno)
Seguridad

Nunca expongas tu token en código público.

Puedes usar variables de entorno:

import os
access_token = os.getenv("FB_ACCESS_TOKEN")
Mejoras futuras
Guardar en formato JSON en lugar de TXT
Manejo de errores más robusto
Logging en lugar de print
Paralelización de requests
Filtrado de datos relevantes
Ejecución
python script.py
📄 Licencia

Este proyecto es de uso libre para fines educativos y de análisis.

Facebook Posts & Comments Extractor

Python script to retrieve posts and comments from a Facebook page using the Graph API and store them in a .txt file.

Description

This project allows you to:

Connect to the Facebook Graph API
Retrieve posts from a page
Extract comments associated with each post
Save the information to a local file
Navigate through multiple pages of results (pagination)
Requirements
Python 3.x
requests library

Installation:

pip install requests
Configuration

Before running the script, configure:

access_token: Valid Facebook access token
{page_id}: Facebook page ID you want to query
api_url = 'https://graph.facebook.com/v17.0/{page_id}/posts'
access_token = '{your_token}'
Code Overview
1. Fetch data from API
def get_posts_data(url):
Sends a GET request to the API
Returns data in JSON format
Handles request errors
2. Save data to file
def save_data_to_file(data, filename):
Iterates through retrieved posts
Saves each post as text in a .txt file
Uses UTF-8 encoding
3. Pagination

The script iterates through multiple result pages:

for i in range(10):
Retrieves up to 10 pages (can be modified)
Uses paging.next to continue fetching data
Output

Data is stored in:

D:\WSD\posts_data_2023.txt

Example format:

{'id': '...', 'comments': {...}}
Considerations
The access token must have proper permissions (e.g., pages_read_engagement)
Facebook API enforces rate limits
Do not upload your access_token to public repositories
Security

Do not expose your token in public code.

Use environment variables instead:

import os
access_token = os.getenv("FB_ACCESS_TOKEN")
Future Improvements
Save data in JSON format instead of TXT
Improve error handling
Use logging instead of print statements
Add parallel requests
Filter relevant data
Execution
python script.py
License

This project is free to use for educational and analytical purposes.
