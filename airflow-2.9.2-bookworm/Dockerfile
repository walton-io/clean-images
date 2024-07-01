FROM docker.io/apache/airflow:2.9.2

USER root
RUN sed -i -e's/ bookworm bookworm-updates/ bookworm bookworm-updates trixie/g' /etc/apt/sources.list.d/debian.sources && \
    cat /etc/apt/sources.list.d/debian.sources &&  \
    apt-get update && \
    apt-get install -y  \
    libnghttp2-14=1.62.1-1 \
    libpython3.11-minimal=3.11.2-6+deb12u2 \
    libsystemd0=252.26-1~deb12u2 \
    libudev1=252.26-1~deb12u2 \
    python3.11-minimal=3.11.2-6+deb12u2 \
    zlib1g 

RUN apt-get autoremove -yqq --purge \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


USER airflow
RUN pip uninstall -y apache-airflow-providers-google==10.19.0
RUN pip uninstall -y gcloud-aio-auth==5.2.2
RUN pip install cryptography==42.0.8