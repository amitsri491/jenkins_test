pipeline{
   agent any
   tools{
       
      maven "MVN3"
      jdk "JDK1.8"
   }
   stages(){
       stage('pullscm'){
           steps{
                git credentialsId: 'github', url: 'git@github.com:amitsri491/jenkins_test.git'
               
           }
       }
           stage('Build'){
               
               steps(){
               
               sh "mvn -Dmaven.test.failure.ignore=true -f api-gateway/ clean package"
               }
               post{
                   success{
                       junit 'api-gateway/target/surefire-reports/*.xml'
                       archiveArtifacts 'api-gateway/target/*.jar'
                       
                   }
                   
                   
               }
               
               
           }
           
           
           
           
       }
       
       
   }
    
    
    
