node 
{
      //echo "GitHub BranhName ${env.BRANCH_NAME}"
      echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      echo "Jenkins Node Name ${env.NODE_NAME}"
      echo "Jenkins Home ${env.JENKINS_HOME}"
      echo "Jenkins URL ${env.JENKINS_URL}"
      echo "JOB Name ${env.JOB_NAME}"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '7')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
properties([[$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
      //properties([[$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([githubPush()])])
def mavenHome = tool name : "maven 3.6.2"
stage('CodeCheckout')
{
git branch: 'development', credentialsId: '33b14771-b858-4cc9-aac8-40a58e2ee672', url: 'https://github.com/navya-devops-applications/Amazon.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
} 
/*stage('GeneratingSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('GeneratingArtifacts')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage('DeployingTApplicationServer')
{
sshagent(['c0cf6f48-ac9d-4ee1-888d-ad36f720e3e5'])
{
sh " scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/Pipeline-scriptedway/target/maven-web-application.war ec2-user@13.127.229.187:/opt/apache-tomcat-9.0.35/webapps"  
}
}
stage('Email')
{
emailext body: '''Build completed suucessfully...

Thnaks,
Navya''', subject: 'Build Status', to: 'navyaguntupalli1@gmail.com'
}*/
}
