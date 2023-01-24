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
    }
}
