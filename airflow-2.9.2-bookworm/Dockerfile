FROM docker.io/apache/airflow:2.9.2

USER root
RUN sed -i -e's/ bookworm bookworm-updates/ bookworm bookworm-updates trixie/g' /etc/apt/sources.list.d/debian.sources && \
    cat /etc/apt/sources.list.d/debian.sources &&  \
    apt-get update && \
    apt-get install -y wget libnghttp2-14=1.62.1-1 zlib1g
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        vim \
    && apt-get autoremove -yqq --purge \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    dpkg list


USER airflow
RUN pip uninstall -y apache-airflow-providers-google==10.19.0
RUN pip uninstall -y gcloud-aio-auth==5.2.2
RUN pip install cryptography==42.0.8
