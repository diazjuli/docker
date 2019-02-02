FROM ruby

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y build-essential sqlite3 nodejs
RUN gem install rails

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

#to build: docker build -t ft-rails:on-build .

#to run app:
#Need to be in a directory with the Dockerfile given in subject
#Need a working rails app in a folder named app
#Run following commands:
#docker build -t ex02 .
#docker run -it --rm -p 3000:3000 ex02
