FROM bitnami/postgresql:16-debian-12 

USER root 


RUN cat /etc/apt/sources.list
RUN echo "deb http://deb.debian.org/debian trixie main" >> /etc/apt/sources.list && \
    cat /etc/apt/sources.list &&  \
    apt-get update && \
    apt-get install -y zlib1g

USER 1001