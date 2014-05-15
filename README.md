This is a simple demo application using Docker to create and run
a Sinatry Ruby application.  I have run this on a Mac through boot2docker with
ports 49000-49900 forwarded.

First build a ruby docker Image:

    $ docker build -t mwarren/ruby ruby

This starts with a base image of dockerfile/ubuntu which can take a while to
download.  Then it compiles and installs ruby.

    $ docker images

The hello image is a Docker image that is somewhat production like.
It's using foreman/thin as a server rather than WEBrick.

The Dockerfile installs bundler, copies data into the container and installs
required gems.

    $ docker build -t mwarren/hello hello
    $ docker run -d -p 49090:4567 mwarren/hello
    $ open localhost:49090
