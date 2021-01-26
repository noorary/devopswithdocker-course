FROM ubuntu:16.04

WORKDIR /docker-project2

COPY script.sh .

RUN apt-get update && apt-get install -y curl

RUN chmod +x script.sh

CMD ./script.sh