# Usando una imagen base de Python 3.6 con Alpine (ligera)
FROM python:3.6-alpine

# Actualizar y preparar el contenedor con pipenv
RUN apk update
RUN pip install --no-cache-dir pipenv

# Definir el directorio de trabajo y copiar los archivos de configuración
WORKDIR /usr/src/app
COPY Pipfile Pipfile.lock bootstrap.sh ./

# Instalar dependencias de la API usando Pipenv
RUN pipenv install

# Copiar el código fuente de la aplicación
COPY . ./

# Exponer el puerto que usará la aplicación
EXPOSE 5000

# Definir el punto de entrada para el contenedor
ENTRYPOINT ["/usr/src/app/bootstrap.sh"]
