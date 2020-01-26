FROM golang

RUN apt-get update && apt-get install unzip -y && apt-get install -y redis-server

COPY ops-interview-task-master.zip .

RUN unzip ops-interview-task-master.zip && cd ops-interview-task-master && make build

ENV DEMO_APP_ADDR=""

ENV DEMO_REDIS_ADDR=0.0.0.0:6379

COPY startscript.sh .

RUN chmod +x startscript.sh

ENTRYPOINT ["./startscript.sh"]

