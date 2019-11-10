# pipeline
## Install Maven
    sudo yum install maven -y
    mvn archetype:generate
    maven-archetype-webapp
    mvn package
## Install Git
    sudo yum install git -y
    git init
    git add 
    git commit -m "first commit"
    git remote add origin repolink.git
    git push -u origin master
## Install Tomcat
    sudo yum install tomcat tomcat-webapps tomcat-admin-webapps -y
    sudo yum install nano -y
    nano /etc/tomcat/server.xml
    sudo systemctl start tomcat
    sudo systemctl enable tomcat
    sudo chmod -R ugo+rw /var/lib/tomcat/webapps/
    cp target/*.war /var/lib/tomcat/webapps/    
## Jenkins installation
    sudo yum install wget -y
    sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
    sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
    sudo yum install jenkins -y
    sudo service jenkins start
    sudo chkconfig jenkins on
    cat /var/lib/jenkins/secrets/initialAdminPassword 
## Docker 
    sudo yum install -y yum-utils \
    device-mapper-persistent-data \
    lvm2
    sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
    sudo yum install docker-ce docker-ce-cli containerd.io -y
    sudo systemctl start docker
## Sonar
    docker run -d --name sonarqube -p 9000:9000 sonarqube
    Execute sonarcube scanner
    sonar.projectKey=github-jenkins-sonar
## Nexus
    docker run -d -p 8181:8081 --name nexus sonatype/nexus3
    Nexus Platform :plugin
    Nexus Repository Manager Publisher :step
    target/test.war