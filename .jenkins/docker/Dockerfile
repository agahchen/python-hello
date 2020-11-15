FROM jenkins/core/there

RUN echo "JENKINS_REF_HOME=$JENKINS_REF_HOME"
RUN find $JENKINS_REF_HOME -type d
RUN echo "JENKINS_HOME=$JENKINS_HOME"
RUN find $JENKINS_HOME -type d
#RUN find / -type d

USER 0
COPY ./contrib/jenkins/configuration $JENKINS_REF_HOME

RUN set -x && \
    chgrp -R 0 $JENKINS_REF_HOME && \
    chmod -R 644 $JENKINS_REF_HOME && \
    chmod -R g+rwX $JENKINS_REF_HOME

COPY $JENKINS_REF_HOME/jobs $JENKINS_HOME/jobs

USER 10001
