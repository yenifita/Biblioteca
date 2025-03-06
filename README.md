El proyecto es una aplicación de biblioteca desarrollada en Flask, con integración de una base de datos en MySQL mediante PyMySQL. Su propósito es permitir la gestión de libros y usuarios dentro de una biblioteca digital. 
La aplicación está diseñada para ser ejecutada localmente o desplegada en contenedores Docker y en la plataforma PythonAnywhere.

Pasos de instalación y ejecución
Clonar el repositorio desde GitHub:
git clone git@github.com:yenifita/Biblioteca.git
cd Biblioteca

Instalar dependencias: Asegúrate de tener Python 3.11 y pip instalados. Luego, instala las bibliotecas necesarias:
pip install Flask PyMySQL Werkzeug Flask-WTF

Ejecutar la aplicación:
python app.py
La aplicación estará corriendo en http://localhost:5000.

Pasos para desplegar en Docker:
Crear el archivo Dockerfile en la raíz del proyecto:
FROM python:3.11
WORKDIR /app
COPY . .
RUN pip install --no-cache-dir Flask PyMySQL Werkzeug Flask-WTF
EXPOSE 5000
CMD ["python", "app.py"]

Construir la imagen de Docker:
docker build -t mi_proyecto_flask .
Subir la imagen a Docker Hub:

Iniciar sesión:
docker login
Etiquetar la imagen:
docker tag mi_proyecto_flask usuario_docker/mi_proyecto_flask
Subir la imagen:
docker push usuario_docker/mi_proyecto_flask

Pasos para desplegar en PythonAnywhere
Crear cuenta en PythonAnywhere.
Configurar entorno virtual:
mkvirtualenv --python=/usr/bin/python3.10 mi_entorno
Subir el proyecto desde GitHub:

Generar clave SSH:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Añadir la clave a GitHub.
Clonar el repositorio:

git clone git@github.com:yenifita/Biblioteca.git
Instalar dependencias:

pip install -r requirements.txt
Configurar la aplicación web:
Ir a la pestaña "Web" y crear una nueva aplicación Flask.
Seleccionar Python 3.10.
Configurar rutas y variables necesarias.
Probar el despliegue: La app estará disponible en la URL que te proporciona PythonAnywhere, como:
arduino
https://yosutor211.pythonanywhere.com/
