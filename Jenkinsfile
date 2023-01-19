pipeline{
    agent any
   
    stages {
        stage('Getting project from Git') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], browser: [$class: 'GithubWeb', repoUrl: 'https://github.com/nawres21/Continuous-Integration.git'], extensions: [], userRemoteConfigs: [[credentialsId: 'ws.id', url: 'https://github.com/nawres21/Continuous-Integration.git']]])
            }
        }
        stage('Cleaning the project') {
            steps{
                sh "mvn -B -DskipTests clean  " 
            }
        }
    }}
