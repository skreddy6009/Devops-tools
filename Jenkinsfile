pipeline { 
 agent { label "docker-slave" }
  stages { 
        /*stage("installing prerequisites") { 
        steps { 
           script { 
              sh """
                    sudo yum install git maven -y  
                    sudo yum install docker -y
                    sudo sleep 5 
                    sudo usermod -aG docker $user 
                    sudo usermod -aG docker root 
                    sudo systemctl enable docker 
                    sudo systemctl start docker
                    sudo chmod 777 /var/run/docker.sock 
                    sudo systemctl restart docker 
                    sudo docker info 
                 """  
              } 
             } 
            } */
           stage("installing SonarQube tool") { 
             steps { 
              script { 
                 sh "docker run -itd --name sonarQube -p 9000:9000 sonarqube:lts-community" 
              } 
            } 
          }
          stage("instlling Nexustool") { 
          steps { 
            script { 
                 sh "docker run -itd --name nexus -p 8081:8081 sonatype/nexus3" 
              } 
            } 
          } 
      } 
  }
