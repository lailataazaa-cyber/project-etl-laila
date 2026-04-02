FROM ghcr.io/dbt-labs/dbt-bigquery:1.9.0

RUN pip install --no-cache-dir google-cloud-bigquery

COPY . /app
WORKDIR /app

ENV DBT_PROJECT_DIR=/app
ENV DBT_PROFILES_DIR=/app

RUN dbt deps

ENTRYPOINT ["dbt"]