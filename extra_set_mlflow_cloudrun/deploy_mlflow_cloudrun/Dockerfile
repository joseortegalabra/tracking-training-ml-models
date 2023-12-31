
FROM python:3.8-slim-buster

# Copiar los archivos del proyecto de MLflow a la imagen de Docker
COPY . /app
WORKDIR /app

# Instala las dependencias necesarias
RUN pip install google-cloud-storage mlflow==2.2.1

# Copia el archivo de credenciales a la imagen de Docker
COPY sa-gcp-mlflow.json /app/sa-gcp-mlflow.json

# Establece la variable de entorno GOOGLE_APPLICATION_CREDENTIALS
ENV GOOGLE_APPLICATION_CREDENTIALS=/app/sa-gcp-mlflow.json

# Establecer el Bucket para la conexión con mlflow
ENV MLFLOW_MODEL_REGISTRY_URI = gs://mlflow_cloudrun

# Inicia el servidor de MLflow
CMD mlflow server --backend-store-uri gs://mlflow_cloudrun/mlflow_backend --default-artifact-root gs://mlflow_cloudrun/mlflow_artifacts --host 0.0.0.0 --port 8080
