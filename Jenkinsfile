node('master')
{

def mavenHome = tool name: "maven3.6.2"

    stage('checkoutsource')
{
    git credentialsId: 'e05a03ce-ac62-44bb-95be-286e99147fc1', url: 'https://github.com/satish-ops/New_proj_dev.git'
}
   stage('build')
{
    sh "${mavenHome}/bin/mvn clean package"
}
   stage('ExecuteSoanrQubeReport')
{
  echo '\'${mavenHome}/bin/mvn clean sonar:sonar'
}
  stage('upload to nexus')

{

  echo '${mavenHome}/bin/mvn clean deploy'
}


  stage('deploy Application to tomcat')
{ 
  sshagent(['647a4516-29ef-4b28-9d4a-9d47c74e5802']) 
  {

    sh " scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.86.240.115:/opt/tomcat/webapps"
}
}

}
