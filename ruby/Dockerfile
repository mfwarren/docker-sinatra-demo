# Ruby environment
#
# VERSION               0.1

FROM dockerfile/ubuntu
MAINTAINER Matt Warren <matt.warren@gmail.com>

RUN apt-get install -y build-essential zlib1g-dev libssl-dev libreadline6-dev libyaml-dev

ADD http://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.2.tar.gz /tmp/

RUN cd /tmp && \
    tar -xzf ruby-2.1.2.tar.gz && \
    cd ruby-2.1.2 && \
    ./configure && \
    make && \
    make install && \
    cd .. && \
    rm -rf ruby-2.1.2 && \
    rm -f ruby-2.1.2.tar.gz \
    gem install bundler
