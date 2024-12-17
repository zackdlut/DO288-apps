FROM registry.access.redhat.com/ubi9/ubi

RUN dnf -y install git
RUN mkdir /gogs-repositories
RUN mkdir /opt/gogs
RUN mkdir /.ssh
WORKDIR /opt/gogs
COPY  gogs ./
COPY  log log
COPY  scripts scripts
USER root
RUN chgrp -R 0 /opt/gogs && chmod -R g=u /opt/gogs
RUN chgrp -R 0 /.ssh && chmod -R g=u /.ssh
RUN chgrp -R 0 /root && chmod -R g=u /root
RUN chgrp  0 / && chmod  g=u /
RUN chgrp -R 0 /gogs-repositories && chmod -R g=u /gogs-repositories
USER 1001
EXPOSE 3000
CMD ./gogs web
