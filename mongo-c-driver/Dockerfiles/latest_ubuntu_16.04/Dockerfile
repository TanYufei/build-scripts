FROM ppc64le/ubuntu:16.04
MAINTAINER "Atul Sowani <sowania@us.ibm.com>"

RUN apt-get update -y && \
    apt-get install -y git gcc g++ automake autoconf libtool \
    make libsasl2-dev mongodb && \
    git clone https://github.com/mongodb/mongo-c-driver.git && \
    cd mongo-c-driver && \
    ./autogen.sh --with-libbson=bundled && \
    make && \
    make install && \
    apt-get remove --purge -y git gcc g++ automake autoconf libtool make && \
    apt-get autoremove -y

EXPOSE 27017

CMD ["/bin/bash"]
