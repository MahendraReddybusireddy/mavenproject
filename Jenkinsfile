pipeline{
    agent any
    tools{
        maven '3.9.2'
    }
     stages{
         stage('check-out'){
             steps{
             git 'https://github.com/SundeepBinaylal/mavenproject.git'
             }
         }
       stage('build'){
           steps{
           
                   sh 'mvn clean install'
              
           }
       }
      stage("deploy"){
       steps{
        sshagent(['deploy_user']) {
           sh "scp -o StrictHostkeyChecking=no /opt/Maheshreddy/WebProject.war root@172.31.88.51:/root/apache-tomcat-8.5.89/webapps"
          }
      }
   }    
 }
}
