FROM java:openjdk-7-jdk

MAINTAINER dcarrass@everis.com


#ENV http_proxy  http://10.121.8.100:8080
#RUN apt-get update

RUN cd /opt && wget https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.4.0/mule-standalone-3.4.0.tar.gz

RUN cd /opt && tar xvzf mule-standalone-3.4.0.tar.gz && rm mule-standalone-3.4.0.tar.gz && ln -s /opt/mule-standalone-3.4.0 /opt/mule

# Define environment variables.
ENV MULE_HOME /opt/mule

# Define mount points.
VOLUME ["/opt/mule/logs", "/opt/mule/apps", "/opt/mule/domains"]

# Define working directory.
WORKDIR /opt/mule

CMD [ "/opt/mule/bin/mule" ]

# Default http port
EXPOSE 8081