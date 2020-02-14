FROM jenkins/jenkins:lts

# admin user
ENV JENKINS_USER mohateam
ENV JENKINS_PASS admin
 
RUN /usr/local/bin/install-plugins.sh git matrix-auth workflow-aggregator docker-workflow blueocean credentials-binding
 
# ignorer des installations non nécessaire 
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=true
 
# lancer le script pour stocker le user admin
COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/
COPY default-user.groovy /usr/share/jenkins/ref/init.groovy.d/


EXPOSE 8089