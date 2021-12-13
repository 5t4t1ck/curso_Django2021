#Compando para conocer la versión de Python instalada

python3 -V

#Crear un nuevo directorio

mkdir project_name

#Crear entorno virtual

python3 -m venv .env

#Activar el entorno virtual en GNU/Linux o Mac

source .env/bin/activate

#Activar el entorno virtual en Windows

cd .env/Scrtipts

activate

#Instalar Django

pip install django

#Crear proyecto nuevo de Django

django-admin startproject config .

#Crear app en Django

python3 manage.py startproject app_name

#Crear las primeras migraciones

python manage.py makemigrations

#Crear las bases de datos y las tablas

python manage.py migrate

#Crear superusuario

python3 manage.py createsuperuser

#Crear el archivo requirements.txt

pip freeze > requirements.txt