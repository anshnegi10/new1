FROM ubuntu:22.04

RUN apt-get update && apt-get install -y python3 python3-pip

RUN pip3 install flask==3.0.*

WORKDIR /app
COPY hello.py /app

ENV FLASK_APP=hello.py

EXPOSE 8000

CMD ["flask", "run", "--host=0.0.0.0", "--port=8000"]