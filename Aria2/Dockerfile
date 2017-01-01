# This is a comment
FROM docker.io/debian
MAINTAINER John Wang
RUN sed -i 's#jessie main#sid main#g' /etc/apt/sources.list
#RUN sed -i 's/wheezy/jessie/g' /etc/apt/sources.list
#RUN sed -i 's/http\./httpredir\./g' /etc/apt/sources.list
#RUN sed -i 's/\.net/\.org/g' /etc/apt/sources.list
#RUN cat /etc/apt/sources.list
#RUN apt-get update
#RUN apt-get remove aria2 -y
#RUN apt-get install aria2 -y

RUN apt-get -q update && apt-get install -y --force-yes --no-install-recommends --auto-remove aria2 && rm -rf /var/lib/apt/lists/*

# aria2.session
ADD aria2.session /etc/aria2/aria2.session

# aria2.conf
ADD aria2.conf /etc/aria2/aria2.conf

# aria2 downloaded callback
ADD download-complete.sh /etc/conf/aria2/download-complete.sh

# add download folder
RUN mkdir -p /data/aria2/download
#RUN mkdir -p /data/aria2/download2
#RUN mkdir -p /data/aria2/download3
#RUN mkdir -p /data/aria2/download4

EXPOSE 6800

# CMD ["/usr/bin/aria2c", "--conf-path=/etc/aria2/aria2.conf", "-D"]
CMD ["/usr/bin/aria2c", "--conf-path=/etc/aria2/aria2.conf"]