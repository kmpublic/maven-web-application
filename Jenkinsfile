

node 
{


def mvnHome = tool name:"maven 3.6.3"

// properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])


stage('CODE')
{
git branch: 'development', credentialsId: 'd3c0cafb-b70d-4fc5-931a-885a68e96ce3', url: 'https://github.com/kmpublic/maven-web-application.git'
}
   

stage('BUILD')
{
sh "${mvnHome}/bin/mvn clean package "
}

/*
stage('SONAR')
{
sh "${mvnHome}/bin/mvn sonar:sonar"
}

stage('NEXUS')
{
sh "${mvnHome}/bin/mvn deploy"
}

stage('DEPLOY')
{
sshagent(['43790073-9ce1-404c-8928-09a21832102f']) 
 {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@15.207.100.79:/opt/apache-tomcat-9.0.39/webapps "
}  
}
*/

stage('MAIL')
{
mail bcc: '', body: '''I am interested in this position. 

 PLEASE FIND ATTACHMENT RESUME''', cc: 'Prathapreddykm@gmail.com', from: '', replyTo: '', subject: 'B ok interested', to: 'kmpr92@gmail.com'
 }
 
}


