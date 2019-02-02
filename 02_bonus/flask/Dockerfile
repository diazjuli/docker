FROM ubuntu

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y vim emacs git
RUN apt-get install -y python python3 python-pip python3-pip
RUN pip install pandas numpy scipy sklearn matplotlib
RUN apt-get install -y sqlite
RUN pip install Flask

#to build: docker build -t flask_env .
#to run:  docker run -it flask_env
