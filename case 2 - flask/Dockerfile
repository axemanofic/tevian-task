FROM ubuntu:20.04

RUN mkdir app
WORKDIR /app

COPY app.py uwsgi.ini requirements.txt ./

RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip3 install -r requirements.txt
RUN mkdir -p storage/task_images

ENTRYPOINT ["uwsgi", "--ini", "uwsgi.ini"]
