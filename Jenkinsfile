node('master')
{
   stage ('conti..download')
   {
       git 'https://github.com/jaldisai/maven.git'
       
   }
   stage ('conti..build')
   {
       sh label: '', script: '''mvn package
'''
   }
   
   stage ('conti..deploy')
   {
       sh label: '', script: '''scp  /home/ubuntu/.jenkins/workspace/myproj-git/webapp/target/webapp.war ubuntu@172.31.4.58:/var/lib/tomcat8/webapps/testapp.war
'''
   }
   stage ('conti..testing')
   {
       git 'https://github.com/jaldisai/selenium-rajender.git'
       sh label: '', script: '''java -jar /home/ubuntu/.jenkins/workspace/myproj-git/testing.jar
'''
   }
   stage ('conti..delivary')
   {
     sh label: '', script: '''scp  /home/ubuntu/.jenkins/workspace/myproj-git/webapp/target/webapp.war ubuntu@172.31.8.228:/var/lib/tomcat8/webapps/prod1app.war
'''  
   }
   
}

