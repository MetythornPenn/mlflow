FROM python:3.10-slim

ARG MLFLOW_VERSION=2.12.1

RUN pip install --no-cache-dir \
        mlflow==${MLFLOW_VERSION} \
        psycopg2-binary \
        boto3 \
        gunicorn \
        prometheus-flask-exporter

# Tiny healthcheck endpoint
ENV MLFLOW_TRACKING_USERNAME=admin \
    MLFLOW_TRACKING_PASSWORD=mlflow

EXPOSE 5000

CMD ["mlflow", "server"]
