FROM ubuntu:14.04

RUN apt-get update -q
RUN apt-get upgrade -y
RUN apt-get install -y ca-certificates openssh-server wget apt-transport-https

#download gitlab and install
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh 
RUN chmod 777 script.deb.sh && ./script.deb.sh 
RUN apt-get install -y gitlab-ce

#RUN apt update && apt install -y tzdata && \
#apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

#to build: docker build -t ex03 .

#to run:  docker run -it -p 8080:80 -p 8022:22 --privileged ex03
