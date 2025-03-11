FROM jenkins/jenkins:lts

# RUN jenkins-plugin-cli --plugins workflow-aggregator git

USER root
RUN apt-get update
RUN curl -sSL https://get.docker.com/ | sh
EXPOSE 8080
EXPOSE 50000