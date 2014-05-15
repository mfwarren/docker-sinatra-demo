FROM mwarren/ruby

RUN gem install bundler

ADD . /data/

WORKDIR /data/
RUN chmod +x run-server.sh

RUN bundle install

EXPOSE 4567

CMD ["/usr/local/bin/foreman","start","-d","/data/"]
