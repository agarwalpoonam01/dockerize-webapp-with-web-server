FROM debian:bullseye-slim

LABEL maintainer="Poonam Agarwal <poonamagarwal01@outlook.com>"
COPY . /api
WORKDIR /api
RUN apt update \
    && apt install -y python3 python3-pip \
    && pip3 install -r requirements.txt \
    && apt-get remove --purge --auto-remove -y && rm -rf /var/lib/apt/lists/*
USER 785
EXPOSE 5000
ENTRYPOINT ["python3", "app.py"]
