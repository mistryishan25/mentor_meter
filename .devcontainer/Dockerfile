# Base image
FROM python:3.10-slim

# Set environment variables
ENV AIRFLOW_HOME=/workspace/airflow

# Install system dependencies
RUN apt-get update \ 
&&  apt-get install -y build-essential default-libmysqlclient-dev nano git \
&& pip install --upgrade pip 

# Install Apache Airflow
ARG AIRFLOW_VERSION=2.7.1  
RUN pip install "apache-airflow==${AIRFLOW_VERSION}" \
    --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-3.10.txt"
# constrains file ensures that we are not getting everything and only gettin the compatible versions so that our code is reproducable

WORKDIR /workspace
