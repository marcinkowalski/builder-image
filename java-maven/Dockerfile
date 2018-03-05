FROM centos:latest
MAINTAINER marcin.kowalski@sabre.com

RUN yum install -y java wget mvn --setopt=tsflags=nodocs && yum -y clean all

LABEL io.k8s.description="builder imges Java8 " \
      io.k8s.display-name="Java8" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,java8" \
      io.openshift.s2i.destination="/opt/app" \
      io.openshift.s2i.scripts-url=image:///usr/local/s2i

RUN adduser --system -u 10001 javauser

#RUN whoami 

RUN mkdir -p /opt/app  && chown -R javauser: /opt/app

COPY ./S2iScripts/ /usr/local/s2i

# RUN chmod u+x /usr/local/s2i/*

# RUN chmod -R 777 /usr/

# RUN chmod -R 777 /usr/local/s2i/

#RUN whoami 

#USER 10001

#RUN whoami 

CMD ["/usr/local/s2i/usage"]
