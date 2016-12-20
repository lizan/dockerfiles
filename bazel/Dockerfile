FROM ubuntu:16.04

RUN apt-get update
RUN apt-get -qy install curl
RUN echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" > /etc/apt/sources.list.d/bazel.list
RUN curl https://bazel.build/bazel-release.pub.gpg | apt-key add -
RUN apt-get update
RUN apt-get -qy install build-essential python bazel uuid-dev
RUN echo "startup --output_base=/source/bazel-output_base" >> /etc/bazel.bazelrc

RUN mkdir /source
WORKDIR /source

RUN bazel version || true

CMD /usr/bin/bazel
