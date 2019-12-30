node('master')
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/jaldisai/maven.git
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: '''scp /home/ubuntu/.jenkins/workspace/Firstproj/webapp/target/webapp.war ubuntu@172.31.4.58:/var/lib/tomcat8/webapps/devapp.war
'''
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/jaldisai/selenium-Rajender.git
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Firstproj/testing.jar'
    }
    stage('ContinuousDelivery')
    {
         sh label: '', script: '''scp /home/ubuntu/.jenkins/workspace/Firstproj/webapp/target/webapp.war ubuntu@18.144.9.252:/var/lib/tomcat8/webapps/prodapp.war
'''
    }


}




