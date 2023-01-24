pipeline{
    agent any
    stages{
        stage('ContinuosDownload'){
            steps{
                git 'https://github.com/thej950/maven.git'
            }
        }
        stage('ContinuosBild'){
            steps{
                sh 'mvn package'
            }
        }
        stage('ContinuosDeployment'){
            steps{
                sh '''scp /var/lib/jenkins/workspace/declarative-pipe-1/webapp/target/webapp.war ubuntu@172.31.32.133:/var/lib/tomcat9/webapps/nava.war'''
            }
        }
        stage('ContinuosTesting'){
            steps{
                git 'https://github.com/thej950/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/declarative-pipe-1/testing.jar'
            }
        }
        stage('ContinuosDelivery'){
            steps{
                sh '''scp /var/lib/jenkins/workspace/declarative-pipe-1/webapp/target/webapp.war ubuntu@172.31.32.133:/var/lib/tomcat9/webapps/thej.war'''
            }
        }
    }
}
