FROM jenkins4eval/jenkins:latest
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false
ENV CASC_JENKINS_CONFIG /usr/share/jenkins/ref/jcasc.yaml
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
COPY jenkins-plugin-manager-2.11.1.jar /usr/share/jenkins/ref/plugin-manager.jar
COPY jcasc.yaml /usr/share/jenkins/ref/jcasc.yaml
# RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
RUN java -jar /usr/share/jenkins/ref/plugin-manager.jar --verbose -f /usr/share/jenkins/ref/plugins.txt 
RUN chown -R jenkins:jenkins /usr/share/jenkins/ref/plugins
# RUN systemctl status jenkins
# RUN systemctl restart jenkins
# RUN systemctl status jenkins