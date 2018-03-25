FROM ruby
ONBUILD COPY . /opt/app

RUN apt-get -y update && \
	apt-get -y upgrade && \
	apt-get -y install nodejs
RUN gem install rails

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
ONBUILD RUN rake db:setup