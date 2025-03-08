# synechron_8th

```

Welcome to OpenDev Etherpad!

This pad text is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents!

OpenDev: https://opendev.org
Etherpad on Github: https://github.com/ether/etherpad-lite


raman khanna


----- jenkins installation :
    
    
    https://www.jenkins.io/download/
    
    
      -- for deployment of jenkins itself : server creation :
        
        region : n virginia
        
        ami: ubuntu 
        
        inst type : t2.micro / t3.micro
        
        rgeenrate a keypair
        
        
        create a sg : raman-sg
        
        storage : 20 gb
        
        
        =============================================================
        
        connect to my instabce using web connect :
            
            sudo -i
        
        jenkins installation :
            
            - https://www.jenkins.io/doc/book/installing/linux/#debian-stable
            
            --  java installation :
                
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.13" 2024-10-15
OpenJDK Runtime Environment (build 17.0.13+11-Debian-2)
OpenJDK 64-Bit Server VM (build 17.0.13+11-Debian-2, mixed mode, sharing)
            
           
            
            


sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
            
            
            
            
    
            
            
-- systemctl status jenkins  
            
            
=====================================
            -- instakll suggest plugins 
            
            
            
cat /var/lib/jenkins/secrets/initialAdminPassword





   26  systemctl status jenkins
   27  vi /usr/lib/systemd/system/jenkins.service
   
   
   
   
   28  systemctl daemon-reload
   29  systemctl restart jenkins
   
   
   ==================================
   
   
   
   
   https://github.com/ramannkhanna2/devops-maven-docker.git
   
   
   
   
   jenkins to completey automate :
   code  >>  maven   >> build >> artefact   >> docker build >> docker image >> docker container 
   
   
   
   --- fork the repository :
       
       https://github.com/ramannkhanna2/devops-maven-docker.git
       
       
       --- code  >>  maven   >> build >> artefact  
       
       
       build steps :
           
mvn clean
mvn package


note : make sure to install maven on the server :
    
    mvn
   18  wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz
   19  ls
   20  tar -xvzf apache-maven-3.9.4-bin.tar.gz 
   21  l
   22  cd apache-maven-3.9.4
   23  ls
   24  cd bin/
   25  ls
   26  ln -s  /root/apache-maven-3.9.4/bin/mvn  /usr/bin/
   
   --------------------------------------------------------------------------------------------------------------------------


-- integarte docker build and container steps in jenkins :
    
    
    mvn clean
mvn package
docker build -t image-name:version .
docker rm -f `docker ps -aq`
docker run -d -p 8081:8080 --name mynewcontainer image-name:version 


====================================================================================





















testing :

docker image >> docker conatiner 


install docker :
    
    https://docs.docker.com/engine/install/ubuntu/
    
   
    mkdir test
   62  cd test
   63  ls
   64  git clone https://github.com/ramannkhanna2/devops-maven-docker.git
   65  ls
   66  cd devops-maven-docker/
   67  ls
   68  rm -rf Jenkinsfile Jenkinsfile-devsecops JenkinsfileNexusAdded  JenkinsfileWithDynamicTags 
   69  ls
   70  cat Dockerfile 
   71  ls
   72  mvn clean package 
   cd target/
   77  ls
   78  cd ..
   79  ls
   80  cat Dockerfile 
   81  ls
   82  docker images
   83  docker ps -a
   84  clea
   85  clear
   86  history
   87  ls
   88  docker build -t ramanimage .
   89  docker images
   90  docker image history
   91  docker image history ramanimage
   92  clear
   93  docker images
   94  docker run -d --name con1 httpd:latest
   95  docker ps
   96  docker exec -it con1 -- /bin/bash
   97  docker exec -it con1 /bin/bash
   98  docker ps -a
   99  docker exec -it con1 ls
  100  docker ps
  101  docker rm -f con1
  102  docker images
  103  docker rmi -f httpd
   
   ===============================

```
