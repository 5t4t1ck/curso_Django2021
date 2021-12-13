# Compando para conocer la versión de Python instalada

    python3 -V

# Crear un nuevo directorio

    mkdir project_name

# Crear entorno virtual

    python3 -m venv .env

# Activar el entorno virtual en GNU/Linux o Mac

    source .env/bin/activate

# Activar el entorno virtual en Windows

    cd .env/Scrtipts

    activate

# Instalar Django

    pip install django

# Crear proyecto nuevo de Django

    django-admin startproject config .

# Crear app en Django

    python3 manage.py startproject app_name

# Crear las primeras migraciones

    python manage.py makemigrations

# Crear las bases de datos y las tablas

    python manage.py migrate

# Crear superusuario

    python3 manage.py createsuperuser

# Crear el archivo requirements.txt

    pip freeze > requirements.txt

# Instalación de archivos desde requirements.txt

    pip install -r requirements.txt

# Otros comandos útiles

# Shell de Django

    python manage.py shell

# Ejemplo de código para correr en shell

    >>> from app_name.models import User

    >>> user1 = User.objects.first()

# Preparar carpeta estatica para produccion

    python3 manage.py collectstatic

# Tomar los datos de la aplicacion y convertirlos en json

    python manage.py dumpdata app_name > myapp.json

# Tomar los datos del archivo json e importar en la tabla de datos de la aplicación

    mython manage.py loaddata myapp.json

# Configurar el directorio config

# Agregar una aplicación en settings.py
    INSTALLED_APPS = [ … , 'app_name' ]

# Agregar carpeta de templates
    crear carpeta appfolder/templates/appname

# Crear carpeta templates del Proyecto: 
    crear carpeta projectname/templates

# Configuración del archivo settings.py 
    Project templates settings.py:
        TEMPLATES = [
        { …
                'DIRS': [BASE_DIR / 'templates', ],
        … }

# Crear carpeta para archivos estaticos: 
    project_name\static\

# Configuración de la carpeta estatica en el archivo (settings.py): 
STATIC_URL = '/static/'
STATICFILES_DIRS = [ BASE_DIR / 'static' ] 
STATIC_ROOT = 'static_root'

# Para utilizar PostgreSQL instalar Psycopg2
    pip install psycopg2
# settings.py
    DATABASE = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'blog',
            'USER': 'admin',
            'PASSWORD': '123456',
            'HOST': 'localhost',
            'PORT': '5432'