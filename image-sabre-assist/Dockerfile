FROM maven:3.5.2-jdk-8
MAINTAINER marcin.kowalski@sabre.com

#RUN yum install -y java wget mvn --setopt=tsflags=nodocs && yum -y clean all

LABEL io.k8s.description="builder imges Java8 " \
      io.k8s.display-name="Java8" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,java8" \
      io.openshift.s2i.destination="/opt/app" \
      io.openshift.s2i.scripts-url=image:///usr/local/s2i

RUN adduser --system -u 10001 javauser

RUN mkdir -p /opt/app  && chown -R javauser: /opt/app

COPY ./S2iScripts/ /usr/local/s2i

RUN chmod -R 777 /usr/local/s2i/

USER 10001

CMD ["/usr/local/s2i/usage"]
