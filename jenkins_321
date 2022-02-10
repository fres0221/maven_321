node('Dev') 
{
    stage('continuousdownload_ master') 
    {
       git 'https://github.com/fres0221/Maven_fareed.git'
    }
    stage('continuousbuild_ master') 
    {
       sh 'mvn package'
    }
    stage('continuousdeployment_ master') 
    {
       sh 'scp /home/ubuntu/.jenkins/workspace/Multipipeline-2_master/webapp/target/webapp.war ubuntu@172.31.80.110:/var/lib/tomcat8/webapps/testing.war'
    }
    stage('continuoustesting_ master') 
    {
       git 'https://github.com/fres0221/functionaltesting_212.git'
       sh 'java -jar /home/ubuntu/.jenkins/workspace/Multipipeline-2_master/testing.jar'
    }
    stage('continuousdelivery_ master') 
    {
       sh 'scp /home/ubuntu/.jenkins/workspace/Multipipeline-2_master/webapp/target/webapp.war ubuntu@172.31.85.10:/var/lib/tomcat8/webapps/prod.war'
    }
    
}
