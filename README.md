
Table of Content

- [Prerequisite](#prerequisite)
- [gcloud](#gcloud)
- [jenkins](#jenkins)





## Prerequisite

  - Docker 


---

## gcloud
- ### Gcloud Docker image for ARM64 Architecture (Raspberry Pi 4)
  - built on [arm64v8/ubuntu](https://hub.docker.com/r/arm64v8/ubuntu)
  - Install GCloud && Updates

-   ### Usage
    - `docker build -t gcloud_arm64:latest .`
    - `docker run -it --rm --privileged --name gcloud gcloud_arm64`

---

## jenkins

- ### Jenkins Configured Docker Image for ARM64 (Raspberry Pi 4)
  - built on [jenkins/jenkins](https://hub.docker.com/r/jenkins/jenkins)
  - install Jenkins plugins using plugins.txt
  - configure Jenkins using [JCasC](https://www.jenkins.io/projects/jcasc/)
  - [Documentation and Instructions](https://www.digitalocean.com/community/tutorials/how-to-automate-jenkins-setup-with-docker-and-jenkins-configuration-as-code)
  - JCASC refrences `server_ip:8080/configuration-as-code/reference`

- ### Usage
  Change the admin user and password
  - `docker build -t jenkins:jcasc .`
  - `docker run -it --name jenkins --rm -p 8080:8080 --env JENKINS_ADMIN_ID=admin --env JENKINS_ADMIN_PASSWORD=password jenkins:jcasc`
  
  or
  - `docker build -t jenkins_arm64:latest .`
  - `docker run -itd --rm --privileged --name jenkins -p 8080:8080 --env JENKINS_ADMIN_ID=admin --env JENKINS_ADMIN_PASSWORD=password --env JENKINS_IP=192.168.4.90:8080 jenkins_arm64`
