FROM ubuntu:latest
COPY . /api
WORKDIR /api
RUN apt update
RUN apt install -y python3 python3-pip
# python3-devel
RUN pip3 install -r requirements.txt
USER 785
EXPOSE 5000
ENTRYPOINT ["python3", "app.py"]