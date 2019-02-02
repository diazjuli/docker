FROM debian:latest

#accept teamspeak server liscence
ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011 30033

RUN apt-get update
RUN apt-get upgrade -y 
RUN apt-get install -y wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.5.0/teamspeak3-server_linux_amd64-3.5.0.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.5.0.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

#to build: docker build -t ex01 .
#to run:  docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01


