FROM centos:7
MAINTAINER @apercova (https://github.com/apercova/)

ENV INSTFILE="jdk-10*linux*.tar.gz" \
    JAVA_HOME="/usr/lib/jvm/default"

ADD ${INSTFILE} /usr/lib/jvm/

RUN ls -l  /usr/lib/jvm/ && \
    export INST_DIR=$(ls -1 -d /usr/lib/jvm/jdk*) && \
    ln -s $INST_DIR /usr/lib/jvm/default && \
    alternatives --install /usr/bin/java java $INST_DIR/bin/java 10000 && \
    alternatives --install /usr/bin/javac javac $INST_DIR/bin/javac 10000 && \
    alternatives --install /usr/bin/jar jar $INST_DIR/bin/jar 10000 
