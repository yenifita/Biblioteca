El proyecto es una aplicación de biblioteca desarrollada en Flask, con integración de una base de datos en MySQL mediante PyMySQL. Su propósito es permitir la gestión de libros y usuarios dentro de una biblioteca digital. 
La aplicación está diseñada para ser ejecutada localmente o desplegada en contenedores Docker y en la plataforma PythonAnywhere.

Instrucciones de instalación y ejecución

    Clonar el repositorio

git clone https://github.com/yenifita/Biblioteca.git
cd Biblioteca

Crear un entorno virtual (opcional, pero recomendado)

python -m venv venv
source venv/bin/activate  # En Windows usar venv\Scripts\activate

Instalar las dependencias

pip install -r requirements.txt

Ejecutar la aplicación

    python app.py

    La aplicación estará disponible en http://localhost:5000.

Pasos para desplegar en Docker

    Crear un Dockerfile en la raíz del proyecto con el siguiente contenido:

FROM python:3.11
WORKDIR /app
COPY . .
RUN pip install --no-cache-dir Flask PyMySQL Werkzeug Flask-WTF
EXPOSE 5000
CMD ["python", "app.py"]

Construir la imagen de Docker

docker build -t mi_proyecto_flask .

Iniciar sesión en Docker Hub

docker login

Etiquetar la imagen con el usuario de Docker Hub

docker tag mi_proyecto_flask usuario_docker/mi_proyecto_flask

Subir la imagen a Docker Hub

docker push usuario_docker/mi_proyecto_flask

Ejecutar el contenedor

    docker run -p 5000:5000 usuario_docker/mi_proyecto_flask

Pasos para desplegar en PythonAnywhere

    Crear una cuenta en PythonAnywhere
        Registrarse en PythonAnywhere.

    Configurar el entorno
        Crear un entorno virtual en la consola de PythonAnywhere:

    mkvirtualenv --python=/usr/bin/python3.11 mi_entorno

Subir el proyecto a GitHub

    Generar una clave SSH y agregarla a GitHub.
    Clonar el repositorio en PythonAnywhere:

    git clone git@github.com:yenifita/Biblioteca.git

Ejecutar la aplicación en PythonAnywhere

    Instalar las dependencias en el entorno virtual:

pip install -r requirements.txt

Configurar el servidor web en PythonAnywhere para que ejecute app.py.
