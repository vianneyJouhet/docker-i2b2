FROM jboss/wildfly:10.1.0.Final

USER root

RUN mkdir /opt/deploy

ADD ./ressources/i2b2core-src.zip /opt/deploy/i2b2core-src.zip
RUN unzip -o /opt/deploy/i2b2core-src.zip -d /opt/deploy/
ADD ./ressources/ont-ds.xml.template /opt/ressources/ont-ds.xml


WORKDIR /opt/deploy/
RUN ls
ADD ./lib/postgresql-42.1.4.jar /opt/jboss/wildfly/standalone/deployments/postgresql-42.1.4.jar
RUN wget https://maven.xwiki.org/externals/com/oracle/jdbc/ojdbc8/12.2.0.1/ojdbc8-12.2.0.1.jar

ADD ./lib/xmlstarlet-1.6.1-1.el7.x86_64.rpm /opt/deploy/xmlstarlet.rpm
RUN rpm -ivh xmlstarlet.rpm

ADD ./lib/apache-ant-1.9.6-bin.zip /opt/deploy/ant.zip
RUN unzip ant.zip -d /opt \
        && mv /opt/apache-ant-1.9.6/ /opt/ant/

ADD ./lib/axis2-1.7.1-war.zip /opt/deploy/axis2-war.zip
RUN unzip -o /opt/deploy/axis2-war.zip


WORKDIR /opt/deploy/

RUN touch deployed
RUN echo 'false'>deployed
ADD ./ressources/parametrage.sh /opt/deploy/parametrage.sh
RUN chmod +x /opt/deploy/parametrage.sh
ADD ./ressources/start.sh /opt/deploy/start.sh
RUN chmod +x /opt/deploy/start.sh

# RUN /opt/deploy/parametrage.sh



CMD ["/opt/deploy/start.sh"]
