DRF Simple Projects API
Una API REST básica construida con Django REST Framework para gestionar proyectos. Desplegada en Render y lista para producción.

🚀 Características
API RESTful completa con CRUD de proyectos

Desplegada en Render con PostgreSQL

Interfaz web de Django REST Framework

Configuración para producción con seguridad HTTPS

Base de datos PostgreSQL en la nube

Documentación automática de la API

📋 Endpoints
Método	Endpoint	Descripción
GET	/api/projects/	Listar todos los proyectos
POST	/api/projects/	Crear nuevo proyecto
GET	/api/projects/{id}/	Obtener proyecto específico
PUT	/api/projects/{id}/	Actualizar proyecto completo
PATCH	/api/projects/{id}/	Actualizar parcialmente proyecto
DELETE	/api/projects/{id}/	Eliminar proyecto
🛠️ Modelo de Proyecto
json
{
  "id": 1,
  "title": "Nombre del proyecto",
  "description": "Descripción detallada del proyecto",
  "technology": "Tecnología utilizada",
  "created_at": "2024-01-15T10:30:00Z"
}
🚀 Despliegue en Render
URL de producción
text
https://drfsimpletest-us6u.onrender.com/api/projects/
Configuración del despliegue
Runtime: Python 3.13.7

Base de datos: PostgreSQL

Servidor: Gunicorn + WhiteNoise

Build Command: ./build.sh

Start Command: gunicorn config.wsgi:application

💻 Instalación local
Prerrequisitos
Python 3.13+

pip

PostgreSQL (opcional, usa SQLite por defecto)

Pasos
bash
# 1. Clonar repositorio
git clone https://github.com/GodofredoNahBurgos/DRFSimpleTest.git
cd DRFSimpleTest

# 2. Crear entorno virtual
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Configurar variables de entorno
# Copia .env.example a .env y edita las variables

# 5. Aplicar migraciones
python manage.py migrate

# 6. Crear superusuario (opcional)
python manage.py createsuperuser

# 7. Ejecutar servidor
python manage.py runserver
📁 Estructura del proyecto
text
DRFSimpleTest/
├── config/                 # Configuración del proyecto Django
│   ├── settings.py        # Configuración principal
│   ├── urls.py           # Rutas principales
│   └── wsgi.py           # WSGI configuration
├── projects/              # App principal
│   ├── models.py         # Modelo Project
│   ├── serializers.py    # Serializador de Project
│   ├── api.py           # ViewSet de la API
│   └── urls.py          # Rutas de la app
├── requirements.txt      # Dependencias de Python
├── build.sh             # Script de build para Render
├── runtime.txt          # Versión de Python
└── README.md            # Este archivo
🔧 Tecnologías utilizadas
Backend: Django 6.0 + Django REST Framework

Base de datos: PostgreSQL (producción) / SQLite (desarrollo)

Despliegue: Render

Servidor: Gunicorn

Archivos estáticos: WhiteNoise

Variables de entorno: python-dotenv

🔐 Seguridad implementada
HTTPS forzado en producción

Cookies seguras (Secure, HttpOnly)

Headers de seguridad XSS y CSRF

DEBUG desactivado en producción

SECRET_KEY desde variables de entorno

🧪 Pruebas
Con Thunder Client/Postman
GET todos los proyectos: GET https://drfsimpletest-us6u.onrender.com/api/projects/

POST crear proyecto:

json
{
  "title": "Mi proyecto",
  "description": "Descripción del proyecto",
  "technology": "Django, React"
}
Con cURL
bash
# Listar proyectos
curl https://drfsimpletest-us6u.onrender.com/api/projects/

# Crear proyecto
curl -X POST https://drfsimpletest-us6u.onrender.com/api/projects/ \
  -H "Content-Type: application/json" \
  -d '{"title": "Nuevo proyecto", "description": "Descripción", "technology": "Python"}'
📊 Estado del proyecto
https://img.shields.io/badge/Render-Deployed-green
https://img.shields.io/badge/Django-6.0-092E20
https://img.shields.io/badge/DRF-3.15-800000

🤝 Contribuir
Fork el proyecto

Crea una rama (git checkout -b feature/nueva-funcionalidad)

Commit cambios (git commit -m 'Añadir nueva funcionalidad')

Push a la rama (git push origin feature/nueva-funcionalidad)

Abre un Pull Request

📄 Licencia
Este proyecto está bajo la licencia MIT. Ver el archivo LICENSE para más detalles.

👤 Autor
GitHub: @GodofredoNahBurgos

API Live: https://drfsimpletest-us6u.onrender.com

🙏 Agradecimientos
Django - El framework web para perfeccionistas con fechas límite

Django REST Framework - Toolkit para construir APIs web

Render - Plataforma de despliegue en la nube

⭐ Si este proyecto te resulta útil, ¡dale una estrella en GitHub!

Este README está diseñado para mostrar tus habilidades técnicas y el proceso completo de despliegue en producción. ¡Perfecto para tu portafolio!