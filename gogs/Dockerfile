FROM registry.access.redhat.com/ubi9/ubi

RUN dnf -y install git
RUN mkdir /opt/gogs
RUN mkdir /.ssh
WORKDIR /opt/gogs
COPY  gogs ./
COPY  log log
COPY  scripts scripts
USER root
RUN chgrp -R 0 /opt/gogs && chmod -R g=u /opt/gogs
RUN chgrp -R 0 /.ssh && chmod -R g=u /.ssh
USER 1001
EXPOSE 3000
CMD ./gogs web
